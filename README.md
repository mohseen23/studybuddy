# ◈ StudyBuddy

**Free peer-to-peer academic support platform for university students.**

Connect with classmates. Share knowledge. Learn together.

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | HTML, CSS, JavaScript, Pug |
| Backend | Node.js, Express.js |
| Database | MySQL 8 |
| DevOps | Docker, Docker Compose |

---

## Quick Start (Docker — Recommended)

### Prerequisites
- [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed

### Run
```bash
git clone <your-repo>
cd studybuddy

docker-compose up --build
```

App will be running at: **http://localhost:3000**

To stop:
```bash
docker-compose down
```

To wipe database and restart fresh:
```bash
docker-compose down -v
docker-compose up --build
```

---

## Manual Setup (Without Docker)

### Prerequisites
- Node.js 18+
- MySQL 8.0

### Steps

1. **Install dependencies**
```bash
npm install
```

2. **Set up MySQL**
```bash
mysql -u root -p < database/schema.sql
```

3. **Configure environment**

Create a `.env` file or export these variables:
```
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_password
DB_NAME=studybuddy
SESSION_SECRET=your-secret-key
PORT=3000
```

4. **Start the server**
```bash
npm start
# or for development with auto-reload:
npm run dev
```

5. Open **http://localhost:3000**

---

## Project Structure

```
studybuddy/
├── backend/
│   ├── app.js                  # Express application
│   ├── config/
│   │   └── db.js               # MySQL connection pool
│   ├── controllers/
│   │   ├── authController.js   # Register, login, logout
│   │   ├── profileController.js
│   │   ├── usersController.js
│   │   ├── listingsController.js
│   │   ├── messagesController.js
│   │   └── dashboardController.js
│   ├── middleware/
│   │   └── auth.js             # Session auth guard
│   └── routes/
│       ├── auth.js
│       └── main.js
├── frontend/
│   ├── views/                  # Pug templates
│   │   ├── layout.pug
│   │   ├── dashboard.pug
│   │   ├── auth/
│   │   ├── profile/
│   │   ├── users/
│   │   ├── listings/
│   │   └── messages/
│   └── public/
│       ├── css/main.css
│       └── js/main.js
├── database/
│   └── schema.sql
├── Dockerfile
├── docker-compose.yml
└── package.json
```

---

## Features

### Authentication
- Register with name, email, password (min 8 chars)
- Login / Logout
- Session-based auth
- Passwords hashed with bcrypt (12 rounds)

### Profile System
- Create & edit profile
- Course, subjects, strengths, weaknesses
- View other users' profiles

### Discovery
- Browse all students
- Search by subject keyword

### Study Listings
- Create "Offer Help" or "Request Help" listings
- Browse and filter all listings
- View listing details

### Messaging
- Message any student directly
- View conversation history
- Unread message count

### Security & Ethics
- Bcrypt password hashing
- Session-based auth
- CSRF-safe forms
- Minimal data collection
- No third-party data sharing
- Report system (schema ready)

---

## Routes

| Method | Route | Description |
|--------|-------|-------------|
| GET | `/auth/register` | Register page |
| POST | `/auth/register` | Submit registration |
| GET | `/auth/login` | Login page |
| POST | `/auth/login` | Submit login |
| GET | `/auth/logout` | Logout |
| GET | `/dashboard` | Dashboard |
| GET | `/profile` | View own profile |
| GET | `/profile/create` | Create profile page |
| POST | `/profile/create` | Save profile |
| GET | `/profile/edit` | Edit profile page |
| POST | `/profile/update` | Update profile |
| GET | `/users` | All students |
| GET | `/users/:id` | Student profile |
| GET | `/search?subject=` | Search by subject |
| GET | `/listings` | All listings |
| GET | `/listings/create` | Create listing page |
| POST | `/listings/create` | Submit listing |
| GET | `/listings/:id` | Listing detail |
| POST | `/listings/:id/delete` | Delete listing |
| GET | `/messages` | Inbox |
| GET | `/messages/:userId` | Conversation |
| POST | `/messages/send` | Send message |

---

## License

MIT — Free to use and modify.
