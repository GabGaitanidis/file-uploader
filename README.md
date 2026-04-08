# Cloudify

A cloud-based file storage web app where users can upload, organize, and download files through a clean folder-based interface.

**Stack:** Node.js · Express · PostgreSQL · Prisma · EJS · Cloudinary

---

## Features

- User registration and login with hashed passwords
- Personal dashboard with a collapsible sidebar for folder navigation
- Create and delete folders
- Upload images into folders (stored on Cloudinary)
- Download or delete individual files
- Session-based authentication

## How It Works

Each user gets their own workspace. Files are uploaded to Cloudinary and their URLs are stored in PostgreSQL via Prisma. Folders group files together and are scoped to the logged-in user.

## Project Structure

```
cloudify/
├── controllers/     # Business logic (auth, folders, files)
├── routes/          # Express route definitions
├── views/           # EJS templates (login, signup, dashboard, folder)
├── public/          # CSS and static assets
├── prisma/          # Schema and migrations
├── app.js           # Entry point
└── db.js            # Prisma client and query functions
```

## Database Schema

| Table   | Description                         |
| ------- | ----------------------------------- |
| Users   | Stores username and hashed password |
| folders | Belongs to a user, contains files   |
| files   | Stores Cloudinary URL and filename  |
| Session | Persists login sessions             |

## Getting Started

### Prerequisites

- Node.js v18+
- PostgreSQL
- Cloudinary account (free tier works)

### Installation

```bash
git clone https://github.com/GabGaitanidis/file-uploader.git
cd file-uploader
npm install
```

### Environment Variables

Create a `.env` file in the root (see `.env.example` for reference):

```env
DATABASE_URL="postgresql://user:password@localhost:5432/dbname"
SESSION_SECRET="your_session_secret"
CLOUDINARY_CLOUD_NAME="your_cloud_name"
CLOUDINARY_API_KEY="your_api_key"
CLOUDINARY_API_SECRET="your_api_secret"
```

### Setup & Run

```bash
npx prisma migrate dev
node app.js
```

Visit `http://localhost:3000`

## What I Learned

- Integrating cloud file storage with Cloudinary and Multer
- Designing relational data models with Prisma (users → folders → files)
- Session persistence using a database-backed session store
- Building a responsive sidebar UI with vanilla JS and CSS
