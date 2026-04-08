# File Uploader

A full-stack file management web application built with Node.js and Express. Users can register, log in, upload files, and organize them into folders — with cloud storage handled via Cloudinary.

## Features

- User authentication (register / login / logout)
- Upload files to personal storage
- Organize files into folders
- View and manage uploaded files
- Persistent storage with PostgreSQL via Prisma ORM

## Tech Stack

- **Runtime:** Node.js
- **Framework:** Express.js
- **Database:** PostgreSQL
- **ORM:** Prisma
- **Templating:** EJS
- **Auth:** Passport.js (session-based)
- **Styling:** CSS

## Project Structure

```
file-uploader/
├── controllers/     # Route handler logic
├── routes/          # Express route definitions
├── views/           # EJS templates
├── public/          # Static assets (CSS, JS)
├── prisma/          # Prisma schema and migrations
├── app.js           # App entry point
└── db.js            # Database connection
```

## Getting Started

### Prerequisites

- Node.js v18+
- PostgreSQL database
- A Cloudinary account (for file storage)

### Installation

```bash
git clone https://github.com/GabGaitanidis/file-uploader.git
cd file-uploader
npm install
```

### Environment Variables

Create a `.env` file in the root directory:

```env
DATABASE_URL=your_postgresql_connection_string
SESSION_SECRET=your_session_secret
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
```

### Database Setup

```bash
npx prisma migrate dev
```

### Run

```bash
node app.js
```

Visit `http://localhost:3000`

## What I Learned

- Handling multipart form data and file uploads with Multer
- Integrating third-party cloud storage (Cloudinary)
- Modeling relational data (users, folders, files) with Prisma
- Session-based authentication with Passport.js
- Structuring an Express app with MVC conventions
