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
    
   > ```bash
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
### Alphonso's feedback: 
#### *What went well*
Great learning to focus on early on! Your explanation of the role of Dev Dependencies is spot on and following a step by step approach is definitely the way to go with documentation.

#### *Even better if*
Try to focus these logs on the *why* of concepts and the *how* of your learning. So in this case it would be useful to see the same approach you've taken (giving a few examples with code snippets) applied to showing use cases of these dependencies streamlining the development process. For example, a code snippet from your project showing the test.js script and a screengrab of the command line output of your tests.

Remember you can edit this file throughout the week, so maybe you'll find it useful to just through a snippet of code you're struggling with when it comes up for coming weeks and then returning to flesh out the document on the Friday. Documenting your struggles accurately can really turn the tide on your End Point Assessment and it will be at least as valuable as any other kind of documentation in future Developer roles.


Thanks Alphonso!
