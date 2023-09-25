## Guidance
Answer the following questions considering the [learning outcomes for this week](https://learn.foundersandcoders.com/course/syllabus/developer/server/learning-outcomes/).
Make sure to record evidence of your processes. You can use code snippets, screenshots or any other material to support your answers.

Do not fill in the feedback section. The Founders and Coders team will update this with feedback on your progress.

## Assessment
### 1. Show evidence of a learning outcome you have achieved this week.
#### Server:
**Understand when to install a Dependency as a Dev Dependency**

These are dependencies that are used during the development and testing phases of a project but are not required for the application to run in a production environment. They include tools, libraries, and utilities that help with tasks such as testing, code linting, code formatting, and development-related workflows.

<ol>
  <li>Navigate to the project directory, run the installation command (we're using ESLint for this example):

  > ```bash
  > npm install eslint --save-dev
  > ```
  </li>
  
  <li>This command tells npm to install ESLint and add it to the `devDependencies` section of your project's `package.json` file.</li>
  
  <li>Create ESLint Configuration (Optional):

  > ```bash
  > npx eslint --init
  > ```
  </li>
</ol>

**Create package.json scripts that run our tests**

Adding scripts to package.json simplifies task execution, improves consistency, automates workflows, and enhances collaboration in Node.js projects, streamlining development and ensuring reliable operations.

<ol>
  <li>Open your `package.json` file.</li>
  <li>Inside the "scripts" section, add a new script entry for running your test. You can name it something like "test" and specify the test command.
    
    > ```json
    > "scripts": {
    >   "test": "node your-test-command.test.js"
    > }
    > ```

  </li>
  <li>Now, you can run the test by executing the following command in your terminal.

    > ```bash
    > npm test
    > ```

  </li>
</ol>


 ### 2. Show an example of a learning outcome you have struggled with and/or would like to re-visit.
> [**Learning outcome...**]  
> [your evidence here]

## Feedback
> [**Course Facilitator name**]  
> [*What went well*]  
> [*Even better if*]
