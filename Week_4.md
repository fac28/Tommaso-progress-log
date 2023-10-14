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

  > ```
  > <form enctype="multipart/form-data>
  > <input type="file" class="file_input" id="avatar" name="avatar" required />
  > ```
  The user submits a <form enctype="multipart/form-data>" containing an <input type="file"> (the enctype is necessary since the usual urlencoded form data doesn't support files).

  > ```
  > const multer = require("multer");
  > ```
  This line imports the "multer" library. Multer is a middleware for handling multipart/form-data, which is commonly used for file uploads in web applications.

  > ```
  > const upload = multer({ storage: multer.memoryStorage() });
  > ```
  Configuration to store uploaded files in memory, which means that files won't be saved to the disk but kept in memory as buffers. This can be useful for processing file     uploads temporarily before saving them to disk.

  > ```
  > const MAX_SIZE = 1000 * 1000 * 5;
  > ```
  We define a constant variable "MAX_SIZE" with a value of 5 megabytes (5 * 1024 * 1024 bytes). This variable sets a maximum size limit for file uploads, and it's used to check if an uploaded file exceeds this size.

  > ```
  > const ALLOWED_TYPES = ["image/jpeg", "image/png"];
  > ```
  Here, an array called "ALLOWED_TYPES" is created, containing the MIME types for JPEG and PNG image files. This array specifies the types of files that are allowed to be uploaded.

  > ```
  > const fileImg = req.file;
  > ```
  Multer provides the file as req.file. This is an object with metadata about the file (like size) and a buffer property. This contains the actual raw contents of the file.

  > ```
  > 
  > ```

  > ```
  > 
  > ```
 
  > ```
  > 
  > ```
   
 ### 2. Show an example of a learning outcome you have struggled with and/or would like to re-visit.
> [**Learning outcome...**]  
> [your evidence here]

## Feedback
> [**Course Facilitator name**]  
> [*What went well*]  
> [*Even better if*]
