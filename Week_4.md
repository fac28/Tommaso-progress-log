## Guidance
Answer the following questions considering the [learning outcomes for this week](https://learn.foundersandcoders.com/course/syllabus/developer/server-side-app/schedule/).
Make sure to record evidence of your processes. You can use code snippets, screenshots or any other material to support your answers.

Do not fill in the feedback section. The Founders and Coders team will update this with feedback on your progress.

## Assessment
 ### 1. Show evidence of a learning outcome you have achieved this week.
 **File uploads and processing:**
> <img src="https://github.com/fac28/Tommaso-progress-log/assets/63957194/050d0653-ed94-4f16-838f-1894bd44e384" alt="Screenshot upload pic form" width="500">

> <img src="https://github.com/fac28/Tommaso-progress-log/assets/63957194/55762f4e-1758-438b-863c-80e3027f8093" alt="Screenshot upload pic js" width="700">
- <strong>Code explanation:</strong>
  
  - The user submits a <form enctype="multipart/form-data>" containing an <input type="file"> (the enctype is necessary since the usual urlencoded form data doesn't support files).
  > ```
  > <form enctype="multipart/form-data>
  > <input type="file" class="file_input" id="avatar" name="avatar" required />
  > ```


  - This line imports the "multer" library. Multer is a middleware for handling multipart/form-data, which is commonly used for file uploads in web applications.
  > ```
  > const multer = require("multer");
  > ``` 


  - Configuration to store uploaded files in memory, which means that files won't be saved to the disk but kept in memory as buffers. This can be useful for processing file     uploads temporarily before saving them to disk.
  > ```
  > const upload = multer({ storage: multer.memoryStorage() });
  > ```


  - We define a constant variable "MAX_SIZE" with a value of 5 megabytes (5 * 1024 * 1024 bytes). This variable sets a maximum size limit for file uploads, and it's used to check if an uploaded file exceeds this size.
  > ```
  > const MAX_SIZE = 1000 * 1000 * 5;
  > ```


  - An array called "ALLOWED_TYPES" is created, containing the MIME types for JPEG and PNG image files. This array specifies the types of files that are allowed to be uploaded.
  > ```
  > const ALLOWED_TYPES = ["image/jpeg", "image/png"];
  > ```

  
  - The POST handler for this form uses the multer middleware to parse the multipart form data. multerrequires you to specify how many files to expect, and what input names to look for (e.g. upload.single("avatar")).
  > ```
  > router.post("/", upload.single("avatar"), (req, res) => { ...
  > ```


  - Multer provides the file as req.file. This is an object with metadata about the file (like size) and a buffer property. This contains the actual raw contents of the file.
  > ```
  > const fileImg = req.file;
  > ```


  - If the conditions are not met, return an error response
  > ```
  > if (!ALLOWED_TYPES.includes(fileImg.mimetype))
  >
  > if (fileImg.size > MAX_SIZE)
  > ```


  - The content of the uploaded file is read from "fileImg.buffer" and converted to a base64-encoded string. This is done to store the file in a specific format for our database.In SQLite the column type is BLOB (binary large object).
  > ```
  > const imageBuffer = fileImg.buffer.toString("base64");
  > ```

  > ```
  > CREATE TABLE IF NOT EXISTS images (
  > id INTEGER PRIMARY KEY AUTOINCREMENT,
  > image_file BLOB NOT NULL
  > );
  > ```

   
 ### 2. Show an example of a learning outcome you have struggled with and/or would like to re-visit.
> **Deployment**] 
> I haven't had a DevOps role yet, so I don' t really know anything about deployment on fly.io (or other platforms really).I guess I'll look more into it next week for the next project!

## Feedback
> [**Course Facilitator name**]  
> [*What went well*]  
> [*Even better if*]
