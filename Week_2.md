## Guidance
Answer the following questions considering the [learning outcomes for this week](https://learn.foundersandcoders.com/course/syllabus/developer/database/learning-outcomes/).
Make sure to record evidence of your processes. You can use code snippets, screenshots or any other material to support your answers.

Do not fill in the feedback section. The Founders and Coders team will update this with feedback on your progress.

## Assessment
 ### 1. Show evidence of a learning outcome you have achieved this week.
 **Design and document a database schema:**  
> <img src="https://github.com/fac28/db-issy-tess-tommaso-james/blob/dev-branch/public/schema.png"></img>

**Create a relational database using SQLite:**
<ol>
 <li>
We first import the "better-sqlite3" library:
  
 > ```bash
 > const Database = require("better-sqlite3")
 > ```
 </li>
<li>
Then create a database instance:

 > ```bash
 > const db = new Database(process.env.DB_FILE)
 > ```
    
 </li> 
 The process.env.DB_FILE variable is used as the path to the SQLite database file. This assumes that the database file path is stored in the DB_FILE environment variable.
>
<li>
 Read the Database Schema from a File:

 > ```bash
 > const schemaPath = join("src", "database", "schema.sql")
 > const schema = readFileSync(schemaPath, "utf-8")
 > ```

In these lines, it reads the database schema from an SQL file located at the path specified by schemaPath. It assumes that the schema file is located in the "src/database" directory and is named "schema.sql."

</li>

<li>
Execute the schema:
 
 > ```bash
 > db.exec(schema)
 > ```

The database schema (SQL commands that define tables, indexes, and constraints) is executed within the SQLite database using the exec method provided by the "better-sqlite3" library. This effectively creates the database schema and sets up the initial structure of the database based on the SQL commands defined in the "schema.sql" file.
</li>

</ol>

**Normalize data to reduce duplication:**
<p>By using the <strong>UNIQUE</strong> constraint we can make sure that the name of the cuisine and of the location will be inserted only once in the db</p>

```
CREATE TABLE IF NOT EXISTS cuisine (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT UNIQUE NOT NULL
);

CREATE TABLE IF NOT EXISTS location (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT,
    street TEXT,
    postcode TEXT,
    UNIQUE(name, street, postcode)
);
```
**Create, read update and delete from our database using SQL queries**
Based on the table above (Location):
<ol>
 <li>
  Insert the name of the area, street and postcode:
  
  >```bash
  > const insert_location = db.prepare(/*sql*/ `
  > INSERT INTO location (name, street, postcode)
  > VALUES ($borough, $address, $postcode)
  > RETURNING id AS location_id
  > `);
  >
  > function createLocation(content) {
  > return insert_location.get(content);
  > }
  >```
  >
  In this case we return the id of the location as "location_id" and we retrieve with the <strong>.get()</strong> method.<br>
  If we don't want any return value we can avoid the
  
  >
  >```bash
  > RETURNING id AS location_id
  > ```
 
  and change the function with a <strong>.run()</strong> method.

  >```bash
  >  function createLocation(content) {
  >  return insert_location.run(content);
  >  }
  >  ```
  
  
 </li>
 
 <li>
 Read everyting about that table:
  
  >```bash
  >  const selectLocation = db.prepare(/*sql*/`
  >  SELECT * FROM location`);
  >
  >  function display() {
  >  return selectLocation.all()
  >  }
 >  ```
 </li>
 
 <li>
 Delete a specific location based on a street, for instance:

  > ```bash
  > const delete_location = db.prepare(/*sql*/ `
  > DELETE FROM location
  > WHERE street = $street
  > `);
  >
  > function deleteLocationByStreet(street) {
  > return delete_location.run({ street });
  > }
 </li> 
</ol>




 ### 2. Show an example of a learning outcome you have struggled with and/or would like to re-visit.
**Left, right and outer JOIN:**

<p>Still unclear to me how to use anything other than the defult <strong>JOIN</strong><br>
Example from my project:</p>

>
> ```bash
> const select_venue_info = db.prepare(/*sql*/ `
>    SELECT
>        v.name AS venueName,
>        l.street AS address,
>        l.name AS borough,
>        l.postcode AS postcode,
>        GROUP_CONCAT(c.name, ', ') AS cuisines
>    FROM venue AS v
>    JOIN location AS l ON v.location_id = l.id
>    LEFT JOIN venue_cuisine AS vc ON v.id = vc.venue_id
>    LEFT JOIN cuisine AS c ON vc.cuisine_id = c.id
>    GROUP BY v.id
> `);
> ```
>
 
## Feedback
> [**Course Facilitator name**]  
> [*What went well*]  
> [*Even better if*]
