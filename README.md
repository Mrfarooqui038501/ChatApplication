# Connectly - Real-Time Chat Application

Connectly is a real-time chat application built with a modern tech stack, featuring user authentication, profile management, and instant messaging with image support. It leverages WebSocket for live updates and Cloudinary for image storage, providing a seamless and interactive user experience.

## Features

- **User Authentication**: Secure signup and login with JWT and cookie-based authentication.
- **Real-Time Messaging**: Send/receive text and image messages instantly via WebSocket (Socket.IO).
- **User Management**: Update profile pictures with Cloudinary integration.
- **Online Status**: Displays real-time online/offline status of users.
- **Sidebar Contacts**: View and filter online users for quick chat initiation.
- **Theme Customization**: Choose from multiple themes powered by DaisyUI.
- **Responsive Design**: Optimized for both desktop and mobile devices.

## Tech Stack

### Backend
- **Node.js**: JavaScript runtime for server-side logic.
- **Express.js**: Web framework for building RESTful APIs.
- **MongoDB**: NoSQL database for users and messages.
- **Mongoose**: ODM for MongoDB schema management.
- **JWT**: JSON Web Tokens for authentication (stored in HTTP-only cookies).
- **Bcrypt.js**: Password hashing for security.
- **Socket.IO**: Real-time communication for messaging and online status.
- **Cloudinary**: Cloud storage for profile pictures and message images.

### Frontend
- **React**: JavaScript library for building the UI.
- **React Router**: Client-side routing for navigation.
- **Zustand**: Lightweight state management for auth, chat, and theme.
- **Axios**: HTTP client for API requests.
- **Lucide-React**: Icon library for UI elements.
- **DaisyUI/Tailwind CSS**: Utility-first CSS framework for styling and theming.
- **React Hot Toast**: Toast notifications for user feedback.

## Installation

### Prerequisites
- Node.js (v20.x or later)
- MongoDB (local or cloud instance like MongoDB Atlas)
- Cloudinary account (for image uploads)

### Setup
 **Clone the Repository**:
   ```bash
   git clone https://github.com/Mrfarooqui038501/ChatApplication.git
   cd Connectly 

# Connectly - Real-Time Chat Application

## Installation

### Backend Setup
```bash
cd backend
npm install
```

### Frontend Setup
```bash
cd ../frontend
npm install
```

## Configure Environment Variables
Create a `.env` file in the `backend` directory with the following:

```env
PORT=5001
MONGODB_URI=<your-mongodb-uri>
JWT_SECRET=<your-jwt-secret>
CLOUDINARY_CLOUD_NAME=<your-cloudinary-cloud-name>
CLOUDINARY_API_KEY=<your-cloudinary-api-key>
CLOUDINARY_API_SECRET=<your-cloudinary-api-secret>
NODE_ENV=development
```
Replace placeholders with your actual values.

### Seed the Database (Optional)
To populate dummy users, run:
```bash
cd backend
node seed.js
```

### Run the Application
#### Start the Backend:
```bash
cd backend
npm start
```

#### Start the Frontend:
```bash
cd ../frontend
npm run dev
```

### Access the Application
Open your browser and go to: `http://localhost:5173`

---

## API Routes

### Authentication (`/api/auth`)
#### Register a New User
**POST** `/signup`
```json
{
  "fullName": "John Doe",
  "email": "john@example.com",
  "password": "password123"
}
```

#### Login a User
**POST** `/login`
```json
{
  "email": "john@example.com",
  "password": "password123"
}
```

#### Logout a User
**POST** `/logout`

#### Update User Profile (Protected)
**PUT** `/update-profile`
```json
{
  "profilePic": "<base64-image-string>"
}
```

#### Check Authentication Status (Protected)
**GET** `/check`

---

### Messages (`/api/messages`)
#### Fetch All Users Except Logged-in User (Protected)
**GET** `/users`

#### Fetch Messages Between Users (Protected)
**GET** `/:id`
**Params:** `id` (receiver’s user ID)

#### Send a Message (Protected)
**POST** `/send/:id`
**Params:** `id` (receiver’s user ID)
```json
{
  "text": "Hello!",
  "image": "<base64-image-string>"
}
```

---

## Usage
- **Sign Up/Login**: Create an account or log in to access the chat interface.
- **View Contacts**: See a list of users in the sidebar; online users are highlighted.
- **Start a Chat**: Click a user to begin messaging; view real-time messages.
- **Send Messages**: Type text or upload images to send messages.
- **Update Profile**: Upload a profile picture from the Profile page.
- **Customize Theme**: Choose a theme from the Settings page.
- **Logout**: Sign out from the navbar.

---

## Project Structure
```
Connectly/
├── backend/
│   ├── controllers/
│   │   ├── auth.controller.js
│   │   └── message.controller.js
│   ├── lib/
│   │   ├── cloudinary.js
│   │   ├── db.js
│   │   ├── socket.js
│   │   └── utils.js
│   ├── middleware/
│   │   └── auth.middleware.js
│   ├── models/
│   │   ├── message.model.js
│   │   └── user.model.js
│   ├── routes/
│   │   ├── auth.route.js
│   │   └── message.route.js
│   ├── seed.js
│   ├── server.js
│   └── .env
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── AuthImagePattern.jsx
│   │   │   ├── ChatContainer.jsx
│   │   │   ├── ChatHeader.jsx
│   │   │   ├── MessageInput.jsx
│   │   │   ├── Navbar.jsx
│   │   │   ├── NoChatSelected.jsx
│   │   │   ├── Sidebar.jsx
│   │   │   └── skeletons/
│   │   ├── constants.js
│   │   ├── lib/
│   │   │   └── axios.js
│   │   ├── pages/
│   │   │   ├── HomePage.jsx
│   │   │   ├── LoginPage.jsx
│   │   │   ├── ProfilePage.jsx
│   │   │   ├── SettingsPage.jsx
│   │   │   └── SignUpPage.jsx
│   │   ├── store/
│   │   │   ├── useAuthStore.js
│   │   │   ├── useChatStore.js
│   │   │   └── useThemeStore.js
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── vite.config.js
│   └── .env
├── README.md
└── package.json
```

---

## Contributing
1. **Fork** the repository.
2. **Create a new branch** (`git checkout -b feature/your-feature`).
3. **Commit your changes** (`git commit -m 'Add your feature'`).
4. **Push to the branch** (`git push origin feature/your-feature`).
5. **Open a Pull Request**.

---

## License
This project is licensed under the **MIT License**.

---

## Contact
For issues or suggestions, please open an issue on the [GitHub repository](https://github.com/Mrfarooqui038501/Connectly) or contact the maintainer at `[armanfarooqui078601@gmail.com]`.   