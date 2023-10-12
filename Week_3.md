# Guidance
Answer the following questions considering the [learning outcomes for this week](https://learn.foundersandcoders.com/course/syllabus/developer/authentication/learning-outcomes/). Make sure to record evidence of your processes. You can use code snippets, screenshots, or any other material to support your answers.

Do not fill in the feedback section. The Founders and Coders team will update this with feedback on your progress.

# Assessment

## 1. Show evidence of a learning outcome you have achieved this week.

**Route handling and middleware setup in your Express.js:**

- **Middleware Registration (server.js):**

  In `server.js`, you use the `server.use("/sign-up", signUpRoutes);` line to specify that any requests with a URL path starting with "/sign-up" should be handled by the `signUpRoutes` router.

  <img src="https://github.com/fac28/Tommaso-progress-log/assets/63957194/ea4edd1b-8a5f-4c57-8b4d-4c1ad5bffd58" alt="Screenshot server.js" width="500">

- **Router Configuration (sign-up.js):**

  In `sign-up.js`, you define the behavior for handling requests to the "/sign-up" path using an instance of the Express router. The router defines two routes:

  - `router.get('/')`: Handles GET requests to the root path ("/") of the "/sign-up" route.
  - `router.post('/')`: Handles POST requests to the root path ("/") of the "/sign-up" route.

- **GET Request Handling (sign-up.js):**

  When a GET request is made to "/sign-up", the code in `router.get('/')` executes. It responds to the GET request by rendering the sign-up page HTML template using `res.send(templates.signUpPage());`.

- **POST Request Handling (sign-up.js):**

  When a POST request is made to "/sign-up" (typically when a user submits a sign-up form), the code in `router.post('/')` executes.

  <img src="https://github.com/fac28/Tommaso-progress-log/assets/63957194/ef4dfe61-aa77-4121-834a-0fb3c10ac441" alt="Screenshot sign-up.js" width="500">

---

**Authentication**

- **Password Encryption:**

  The code securely stores user passwords in the database by saving the bcrypt-generated hash of the password. Instead of storing the actual password, only the hash is stored. This is important because it prevents anyone with access to the database from easily retrieving the original passwords. Bcrypt not only hashes passwords but also automatically includes the concept of salting, generating a unique salt for each password hash, making it even more secure.

  <img src="https://github.com/fac28/Tommaso-progress-log/assets/63957194/6a893fc6-6a9d-457b-a764-75ac256aeba5" alt="Screenshot sign-up.js" width="500">

  * **Protection Against Data Breaches:**
    Storing plain text passwords in a database is a security risk. If the database is ever compromised, all user passwords would be exposed. Hashing and salting passwords ensure that even if the database is breached, attackers cannot easily determine the original passwords.

  * **Unique Salts:**
    Salting passwords with unique salts means that even if multiple users have the same password, their hashed passwords will differ due to the unique salts. This prevents attackers from recognizing identical passwords by comparing hash values.

  * **Slow Hashing Algorithm:**
    Bcrypt is intentionally slow, making it computationally expensive for attackers to perform brute-force or dictionary attacks. This slows down any attempts to crack hashed passwords.

---

**Configure ESLint to catch common JS errors:**

- Run the following command in the terminal:

  > ```bash
  > npm init @eslint/config
  > ```

- Set up (basic) config:

  <img src="https://github.com/fac28/Tommaso-progress-log/assets/63957194/3c9c14ae-7472-4b1f-a1f2-20f085c5bdac" alt="Screenshot eslint config terminal" height="150">

- This will create a `.eslintrc.js` file in your directory that can be configured:

  <img src="https://github.com/fac28/Tommaso-progress-log/assets/63957194/d7346182-03d8-4dd2-bdde-8e68f73cc888" alt="Screenshot eslintrc.js" height="400">

  * A linter is a critical code analysis tool that benefits developers in numerous ways. It detects syntax errors, runtime issues, and coding mistakes, preventing problems upfront. Linters enforce coding standards, enhancing code quality, readability, and maintainability. They ensure consistent code style, fostering teamwork. Additionally, they uncover security vulnerabilities and suggest performance improvements. Linters can also encourage thorough code documentation. By integrating linters, developers enjoy increased productivity, reduced debugging efforts, and a high-quality, secure, and organized codebase.




 ### 2. Show an example of a learning outcome you have struggled with and/or would like to re-visit.
> [**Learning outcome...**]  
> [your evidence here]

## Feedback
> Beth

> Your explanation and utilisation of route handling and middleware setup in Express.js is organised and thorough 👌

> To level up your middleware, you might want to consider implementing error handling.
Read more here: [expressjs.com](https://expressjs.com/en/guide/error-handling.html)
Your ESLint configuration looks good. Consider discussing or demonstrating how you deal with linting errors or warnings when they arise. Do you fix them immediately? Do you adjust rules in your configuration based on the team's coding style?

