# 🚀 DevTrack — Developer Task & Time Tracker API

DevTrack is a powerful and flexible API for managing developer productivity. Built with **NestJS** and **PostgreSQL**, it enables users to manage projects, assign tasks, track time, and generate reports.

---

## 📚 Features

### 👥 User & Auth
- JWT authentication with role-based access (`Admin`, `Manager`, `Developer`)
- Secure password hashing using bcrypt
- User registration, login, and profile endpoints

### 🗂️ Project & Task Management
- Create and manage projects
- Assign developers and managers to projects
- Create, assign, and update tasks with priority and status

### ⏱️ Time Tracking
- Start, pause, and stop timers
- Manual time logging
- View time logs per task, user, or project

### 📊 Reporting
- Weekly and daily time reports
- Task status analytics
- Project-level summaries

### 🛡️ Admin Features
- User management
- Timer monitoring and control
- System usage insights

---

## 🧱 Tech Stack

| Layer         | Tech                        |
|---------------|-----------------------------|
| Backend       | NestJS                      |
| ORM           | TypeORM / Prisma            |
| Auth          | Passport + JWT              |
| Database      | PostgreSQL                  |
| Docs          | Swagger (OpenAPI)           |
| Dev Tools     | Docker, Postman, Faker.js   |

---

## 🛠️ Setup Instructions

```bash
# 1. Clone the repo
git clone https://github.com/yourname/devtrack-api.git
cd devtrack-api

# 2. Install dependencies
npm install

# 3. Create and fill your .env file
cp .env.example .env

# 4. Run the database migration
npm run typeorm migration:run

# 5. Start the server
npm run start:dev
