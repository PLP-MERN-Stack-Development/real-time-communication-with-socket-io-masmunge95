# Palaver: Real-Time Chat Application

## 🚀 Project Overview

Palaver is a full-featured, real-time chat application built with the MERN stack (MongoDB, Express, React, Node.js) and Socket.IO. It provides a seamless and interactive communication experience, featuring secure authentication with Clerk, private and global chat rooms, and a host of advanced functionalities including message reactions, editing, deletion, and rich media sharing. The project is designed to be performant, responsive, and user-friendly, showcasing modern web development practices.

## 📸 Screenshots

| Landing Page View | Chat Page View |
|:--------------------:|:---------------------:|
| <img src="client/public/Landing-page-view.png" alt="Landing Page View" height="220" /> | <img src="client/public/Chat-page-view.png" alt="Chat Page View" height="220" /> |

| Mobile Responsive View |
|:----------------------:|
| <img src="client/public/Small-screen-view.png" alt="Mobile Responsive View" height="220" /> |

## Deployment

The application is deployed and live at the following URLs:

- **Frontend (Netlify):** [https://palaver-chat.netlify.app/](https://palaver-chat.netlify.app/)
- **Backend (Render):** [https://real-time-communication-with-socket-io-q2y7.onrender.com/](https://real-time-communication-with-socket-io-q2y7.onrender.com/)

### Deployment Instructions

To deploy your own version of this application, follow these steps:

#### 1. Backend on Render

- Create a new **Web Service** on Render and connect your GitHub repository.
- **Root Directory**: `server`
- **Build Command**: `npm install`
- **Start Command**: `npm start`
- Add the following Environment Variables:
  - `MONGO_URI`: Your MongoDB connection string.
  - `CLERK_SECRET_KEY`: Your secret key from your Clerk production instance.
  - `CLIENT_URL`: The URL of your deployed Netlify frontend (e.g., `https://your-app-name.netlify.app`).

#### 2. Frontend on Netlify

- Create a new site on Netlify and connect it to your GitHub repository.
- **Base directory**: `client`
- **Build command**: `npm run build`
- **Publish directory**: `client/build`
- Add the following Environment Variables in your site settings:
  - `REACT_APP_CLERK_PUBLISHABLE_KEY`: Your publishable key from your Clerk production instance.
  - `REACT_APP_API_URL`: The URL of your deployed Render backend (e.g., `https://your-app-name.onrender.com`).

After setting up both services, your application will be live. Remember to update your Clerk instance with the deployed URLs for proper authentication redirects.

## 🛠️ Setup Instructions

To get the project running locally, please follow these steps:

### Prerequisites

- Node.js (v18 or higher)
- npm (or yarn)
- MongoDB (a local instance or a cloud-based service like MongoDB Atlas)

### 1. Clone the Repository

```bash
git clone https://github.com/masmunge95/real-time-communication-with-socket-io-masmunge95.git
cd palaver-chat
```

### 2. Server Setup

```bash
cd server
npm install
```

Create a .env file in the server directory (you can copy .env.example as a template) and add your secret keys:

```
MONGO_URI=<your_mongodb_connection_string>
CLERK_SECRET_KEY=<your_clerk_secret_key>
CLIENT_URL=http://localhost:3000
```

### 3. Client Setup

```bash
cd client
npm install
```

Create a `.env` file in the `client` directory (you can copy `.env.example` as a template) and add your Clerk Publishable Key:

```
REACT_APP_CLERK_PUBLISHABLE_KEY=<your_clerk_publishable_key>
```

### 4. Start the Application

Run both the server and the client in separate terminals:

```bash
# In the server directory
npm run dev

# In the client directory
npm start
```

The application should now be running, with the client available at `http://localhost:3000` and the server at `http://localhost:5000`.

## 📂 Project Structure

```plaintext
socketio-chat/
├── client/                 # React front-end application
│   ├── public/             # Static assets and index.html
│   ├── src/                # Main source code
│   │   ├── components/     # Reusable UI components (MessageList, UserInput, etc.)
│   │   ├── context/        # React Context for global state (ChatContext)
│   │   ├── hooks/          # Custom hooks for shared logic (useChatSocket)
│   │   ├── pages/          # Page-level components (ChatPage, LandingPage)
│   │   └── socket/         # Client-side Socket.IO setup
│   └── package.json        # Client-side dependencies and scripts
├── server/                 # Node.js back-end server
│   ├── config/             # Configuration files (e.g., database connection)
│   ├── controllers/        # Logic for handling Socket.IO events (chatController.js)
│   ├── models/             # Mongoose schemas for database models (Message.js)
│   ├── public/             # Publicly served static files
│   │   └── uploads/        # Directory for user-uploaded files
│   ├── socket/             # Server-side Socket.IO initialization
│   ├── utils/              # Utility functions (e.g., user management)
│   └── package.json        # Server-side dependencies and scripts
└── README.md
```

## ✨ Features Implemented

### Core Functionality
- **Secure User Authentication**: Integrated with Clerk for robust and secure user sign-up and sign-in.
- **Real-Time Messaging**: Instant message delivery in both global and private chats using Socket.IO.
- **Global & Private Chat Rooms**: A main "Global Chat" for all users and the ability to start private, one-on-one conversations.
- **User Presence**: Real-time display of online/offline status for all users.
- **Typing Indicators**: See when another user is typing in both global and private chats.

### Advanced Features
- **Message Reactions**: Add emoji reactions to any message. Click a reaction to see who reacted.
- **Message Editing**: Edit your own sent messages in-place.
- **Message Deletion**: Delete your own sent messages, removing them for all users in the chat.
- **Read Receipts**: See when your private messages have been read with a double-check icon.
- **Rich Media Sharing**: Share images, videos, and audio files with in-app playback, as well as other file types with a clear download link.

### Notifications & UX
- **Browser & Sound Notifications**: Receive desktop and audio notifications for new messages when the app is not in focus.
- **Unread Message Counts**: See a badge with the number of unread messages for each chat.
- **Message Pagination**: Load older messages on demand with a "Load More" button.
- **Message Search**: A powerful, indexed search allows users to find past messages.
- **Responsive Design**: A mobile-first design that works seamlessly on both desktop and mobile devices, featuring a collapsible user list.
- **Message Delivery Status**: Optimistic UI with status icons for "sending," "sent," and "read" states.
