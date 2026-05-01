# Talksy

Talksy is a real-time chat application built with a modern full-stack setup. It features secure user authentication, live messaging, profile management, and image uploads across a React frontend and a Node.js backend.

## Features

- Email-based OTP verification for secure signup
- JWT authentication with HTTP-only cookies
- Real-time chat powered by Socket.IO
- Contact search and active chat sidebar
- Text and image messaging support
- Profile picture management
- MongoDB-backed persistence for users, messages, and OTP records

## Tech Stack

- Frontend: React, Vite, Tailwind CSS, Zustand, Axios, React Router
- Backend: Node.js, Express, MongoDB, Mongoose, Socket.IO
- Authentication: JWT
- Email: Nodemailer
- Image upload: Cloudinary

## Repository Structure

- `backend/` - Express API server, database models, authentication, messaging logic
- `frontend/` - React application, UI components, pages, and client state management

## Setup

### Prerequisites

- Node.js 18 or newer
- MongoDB database
- Cloudinary account for image uploads
- Gmail account with app password for OTP email delivery

### Install dependencies

```bash
npm install --prefix backend
npm install --prefix frontend
```

### Environment variables

Create a `.env` file inside `backend/` with these variables:

```env
PORT=8080
NODE_ENV=development
MONGO_URL=<your-mongodb-connection-string>
JWT_SECRET=<your-jwt-secret>
OTP_SECRET=<your-otp-secret>
EMAIL=<your-gmail-address>
PASSWORD=<your-gmail-app-password>
CLOUDINARY_CLOUD_NAME=<your-cloudinary-cloud-name>
CLOUDINARY_API_KEY=<your-cloudinary-api-key>
CLOUDINARY_API_SECRET=<your-cloudinary-api-secret>
```

### Run the app

Start the backend server:

```bash
npm run dev --prefix backend
```

Start the frontend app:

```bash
npm run dev --prefix frontend
```

Open `http://localhost:5173` in your browser.

## Production

Build the frontend and serve it from the Express backend when `NODE_ENV=production`:

```bash
npm run build
npm start
```

## Notes

- In development, the frontend uses `http://localhost:8080/api` for backend requests.
- Ensure MongoDB is reachable via `MONGO_URL` before using authentication or messaging.
- OTP emails require a valid Gmail app password.

## License

MIT
