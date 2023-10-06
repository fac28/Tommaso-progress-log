## Guidance
Answer the following questions considering the [learning outcomes for this week](https://learn.foundersandcoders.com/course/syllabus/developer/authentication/learning-outcomes/).
Make sure to record evidence of your processes. You can use code snippets, screenshots or any other material to support your answers.

Do not fill in the feedback section. The Founders and Coders team will update this with feedback on your progress.

## Assessment
 ### 1. Show evidence of a learning outcome you have achieved this week.
 **Route handling and middleware setup in your Express.js:**

   - #### Middleware Registration (server.js): 
     
     In `server.js`, you use the `server.use("/sign-up", signUpRoutes);` line to specify that any requests with a URL path starting with "/sign-up" should be handled by the `signUpRoutes` router.

     <img src="https://github.com/fac28/Tommaso-progress-log/assets/63957194/ea4edd1b-8a5f-4c57-8b4d-4c1ad5bffd58" alt="Screenshot server.js" width="500">

   - #### Router Configuration (sign-up.js): 

     In `sign-up.js`, you define the behavior for handling requests to the "/sign-up" path using an instance of the Express router. The router defines two routes:

     - `router.get('/')`: Handles GET requests to the root path ("/") of the "/sign-up" route.
     - `router.post('/')`: Handles POST requests to the root path ("/") of the "/sign-up" route.

   - GET Request Handling (sign-up.js):

     When a GET request is made to "/sign-up", the code in `router.get('/')` executes. It responds to the GET request by rendering the sign-up page HTML template using `res.send(templates.signUpPage());`.

   - POST Request Handling (sign-up.js):

     When a POST request is made to "/sign-up" (typically when a user submits a sign-up form), the code in `router.post('/')` executes.

     <img src="https://github.com/fac28/Tommaso-progress-log/assets/63957194/ef4dfe61-aa77-4121-834a-0fb3c10ac441" alt="Screenshot sign-up.js" width="500">


**Authentication**

   - ##### Password Encryption:

The code securely stores user passwords in the database by saving the bcrypt-generated hash of the password. Instead of storing the actual password, only the hash is stored. This is important because it prevents anyone with access to the database from easily retrieving the original passwords. Bcrypt not only hashes passwords but also automatically includes the concept of salting, generating a unique salt for each password hash, making it even more secure.


 <img src="https://github.com/fac28/Tommaso-progress-log/assets/63957194/6a893fc6-6a9d-457b-a764-75ac256aeba5" alt="Screenshot sign-up.js" width="500">

<ul>
 <li><strong>Protection Against Data Breaches</strong>:
Storing plain text passwords in a database is a security risk. If the database is ever compromised, all user passwords would be exposed. Hashing and salting passwords ensure that even if the database is breached, attackers cannot easily determine the original passwords.</li>
 <li>
  <strong>Unique Salts</strong>:
Salting passwords with unique salts means that even if multiple users have the same password, their hashed passwords will differ due to the unique salts. This prevents attackers from recognizing identical passwords by comparing hash values.
 </li>
 <li><strong>Slow Hashing Algorithm</strong>:
- Bcrypt is intentionally slow, making it computationally expensive for attackers to perform brute-force or dictionary attacks. This slows down any attempts to crack hashed passwords.
</li>
</ul>



 ### 2. Show an example of a learning outcome you have struggled with and/or would like to re-visit.
> [**Learning outcome...**]  
> [your evidence here]

## Feedback
> [**Course Facilitator name**]  
> [*What went well*]  
> [*Even better if*]
