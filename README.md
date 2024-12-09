# 0x04. Files Manager

## Overview

This project is a summary of key back-end concepts, including authentication, Node.js, MongoDB, Redis, pagination, and background processing. The objective is to build a platform for uploading and viewing files with features such as user authentication, file uploads, and generating image thumbnails.

---

## Learning Objectives

By the end of this project, you should be able to explain the following without external help:

- How to create an API with Express.js.
- How to authenticate users.
- How to store data in MongoDB.
- How to store temporary data in Redis.
- How to set up and use a background worker.

---

## Resources

- [Node.js Getting Started](https://nodejs.org)
- [Process API Documentation](https://nodejs.org/api/process.html)
- [Express.js Getting Started](https://expressjs.com)
- [Mocha Documentation](https://mochajs.org)
- [Nodemon Documentation](https://nodemon.io)
- [MongoDB Documentation](https://www.mongodb.com)
- [Redis Documentation](https://redis.io)
- [Bull Library](https://github.com/OptimalBits/bull)
- [Image Thumbnail Library](https://www.npmjs.com/package/image-thumbnail)
- [Mime-Types Library](https://www.npmjs.com/package/mime-types)

---

- `package.json`
- `.eslintrc.js`
- `babel.config.js`

Run the following command after cloning the repository:

```bash
npm install
```

---

## Tasks

| Task # | Filename(s)                                                                                  | Description                                                                                                          |
|--------|----------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| 0      | [utils/redis.js](./utils/redis.js)                                                           | Create a Redis utility class for managing Redis connections and performing common operations.                        |
| 1      | [utils/db.js](./utils/db.js)                                                                 | Create a MongoDB utility class for managing connections and performing operations like counting users or files.       |
| 2      | [server.js](./server.js), [routes/index.js](./routes/index.js), [controllers/AppController.js](./controllers/AppController.js) | Set up a basic Express.js server and implement endpoints for checking service status and database statistics.         |
| 3      | [routes/index.js](./routes/index.js), [controllers/UsersController.js](./controllers/UsersController.js) | Implement an endpoint to create new users in MongoDB, with proper validations and hashed passwords.                  |
| 4      | [routes/index.js](./routes/index.js), [controllers/UsersController.js](./controllers/UsersController.js), [controllers/AuthController.js](./controllers/AuthController.js) | Implement user authentication and token-based session management.                                                   |
| 5      | [routes/index.js](./routes/index.js), [controllers/FilesController.js](./controllers/FilesController.js), [utils/](./utils/) | Add a POST `/files` endpoint to upload files. Handles file validation, creates files locally, and stores metadata in the database. |
| 6      | [routes/index.js](./routes/index.js), [controllers/FilesController.js](./controllers/FilesController.js) | Add GET `/files/:id` and GET `/files` endpoints to retrieve file metadata by ID or list files with pagination.                    |
| 7      | [routes/index.js](./routes/index.js), [controllers/FilesController.js](./controllers/FilesController.js) | Add PUT `/files/:id/publish` and PUT `/files/:id/unpublish` endpoints to toggle the `isPublic` status of files.                   |
| 8      | [routes/index.js](./routes/index.js), [controllers/FilesController.js](./controllers/FilesController.js) | Add GET `/files/:id/data` endpoint to return file contents if the file is accessible and valid.                                    |
| 9           | [`utils/`](./utils/), [`controllers/FilesController.js`](./controllers/FilesController.js), [`worker.js`](./worker.js) | **Image Thumbnails**: Enhance the `POST /files` endpoint to queue background thumbnail generation for uploaded image files. Use Bull to create a `fileQueue`, process jobs for generating thumbnails (100px, 250px, 500px widths), and append resized files to the original file's location. Update `GET /files/:id/data` to support size-specific file retrieval.                                                                       |
| 10          | [`tests/`](./tests/)                                                                            | **Tests!**: Develop comprehensive tests for all modules and endpoints, including Redis and DB clients, and all API endpoints like `/status`, `/stats`, `/users`, `/connect`, `/disconnect`, `/files`, etc. Ensure proper pagination testing for `GET /files`.                                                                                                                                                                          |
| 11          | [`utils/`](./utils/), [`worker.js`](./worker.js), [`controllers/UsersController.js`](./controllers/UsersController.js) | **New User - Welcome Email**: Update `POST /users` to queue a background job for sending a welcome email when a new user is added. Use Bull to create a `userQueue` to process jobs. Validate `userId` presence in jobs, fetch user from DB, and print `Welcome <email>!` to the console. For production, integrate with services like Mailgun for email delivery.                                                                            |

---

## Setup Environment

To set up the project environment:

1. Clone the repository:
   ```bash
   git clone https://github.com/rofeeqshittu/alx-files_manager.git
    ```
2. Navigate to the project directory:
    ```bash
    cd alx-files_manager
    ```

3. Install dependencies:
    ```bash
    npm install
    ````

4. Start the server:
    ```bash
    npm run start-server
    ```

---
