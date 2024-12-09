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

---

## Setup Environment

To set up the project environment:

1. Clone the repository:
   ```bash
   git clone https://github.com/your_username/alx-files_manager.git
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
