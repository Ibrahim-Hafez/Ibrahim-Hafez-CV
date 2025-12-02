# Ibrahim-Hafez-CV[README.md](https://github.com/user-attachments/files/23887023/README.md)
# Interactive Professional Portfolio

A modern, dynamic portfolio website built with React, TypeScript, and Node.js featuring smooth animations, interactive elements, and a content management system.

## Features

- ✨ Smooth animations with Framer Motion
- 📱 Fully responsive design
- 🎨 Modern, clean UI
- 📧 Contact form with email integration
- 🔍 Project filtering and showcase
- 📄 Downloadable CV (PDF/TXT)
- 🔐 Admin panel for content management
- ⚡ Fast performance with Vite

## Tech Stack

**Frontend:**
- React 19
- TypeScript
- Framer Motion
- React Hook Form
- Axios
- Vite

**Backend:**
- Node.js
- Express
- TypeScript
- Nodemailer
- Puppeteer
- JWT Authentication

## Getting Started

### Prerequisites

- Node.js (v18 or higher)
- npm or yarn

### Installation

1. Clone the repository
```bash
git clone <your-repo-url>
cd interactive-portfolio
```

2. Install dependencies for all packages
```bash
npm run install:all
```

Or install manually:
```bash
# Install root dependencies
npm install

# Install frontend dependencies
cd frontend
npm install

# Install backend dependencies
cd ../backend
npm install
```

3. Configure environment variables

**Frontend** (`frontend/.env`):
```
VITE_API_URL=http://localhost:5000/api
```

**Backend** (`backend/.env`):
```
PORT=5000
NODE_ENV=development

# Email Configuration
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your-email@gmail.com
EMAIL_PASSWORD=your-app-password
EMAIL_FROM=your-email@gmail.com
EMAIL_TO=your-email@gmail.com

# Admin Authentication
ADMIN_USERNAME=admin
ADMIN_PASSWORD_HASH=<bcrypt-hash-of-your-password>
JWT_SECRET=your-secret-key-change-this

# CORS
FRONTEND_URL=http://localhost:5173
```

### Running the Application

**Development mode (runs both frontend and backend):**
```bash
npm run dev
```

**Run frontend only:**
```bash
npm run dev:frontend
```

**Run backend only:**
```bash
npm run dev:backend
```

The frontend will be available at `http://localhost:5173`
The backend API will be available at `http://localhost:5000`

### Building for Production

```bash
npm run build
```

This will build both frontend and backend for production.

## Project Structure

```
interactive-portfolio/
├── frontend/                 # React frontend
│   ├── src/
│   │   ├── components/      # React components
│   │   ├── types/           # TypeScript types
│   │   ├── utils/           # Utility functions
│   │   ├── App.tsx          # Main App component
│   │   └── main.tsx         # Entry point
│   └── package.json
├── backend/                  # Express backend
│   ├── src/
│   │   ├── routes/          # API routes
│   │   ├── services/        # Business logic
│   │   ├── types/           # TypeScript types
│   │   └── server.ts        # Server entry point
│   ├── data/
│   │   └── portfolio.json   # Portfolio data
│   └── package.json
└── package.json             # Root package.json
```

## Customization

### Update Portfolio Data

Edit `backend/data/portfolio.json` to update your personal information, skills, experience, projects, and achievements.

### Email Configuration

To enable the contact form:

1. Use Gmail with an App Password:
   - Go to your Google Account settings
   - Enable 2-Factor Authentication
   - Generate an App Password
   - Use this password in `EMAIL_PASSWORD`

2. Or use another SMTP service by updating `EMAIL_HOST` and `EMAIL_PORT`

### Admin Panel

To access the admin panel:

1. Generate a password hash:
```bash
cd backend
node -e "const bcrypt = require('bcrypt'); bcrypt.hash('your-password', 10, (err, hash) => console.log(hash));"
```

2. Update `ADMIN_PASSWORD_HASH` in `backend/.env`

3. Access the admin panel at `/admin` (implementation pending)

## API Endpoints

- `GET /api/portfolio` - Get portfolio data
- `POST /api/contact` - Send contact message
- `GET /api/download/:format` - Download CV (pdf/txt)
- `POST /api/admin/login` - Admin login
- `PUT /api/admin/portfolio` - Update portfolio (protected)

## License

MIT

## Author

Ibrahim Hafez
