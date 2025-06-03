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
```
## 📋 Task Breakdown :
### ✅ Phase 1: Project Setup
 - Initialize NestJS project with config setup

 -  Setup .env configuration and validation

 - Integrate PostgreSQL with TypeORM or Prisma

 - Add global validation pipes and exception filters

 - Implement global success/error response interceptors

### 🔐 Phase 2: Auth & Users
 - Create User entity with role field (Admin, Manager, Developer)

 - Register and login endpoints using JWT

 - Secure password hashing using bcrypt

 - Auth guards and role-based access (RolesGuard)

 - Endpoint: Get current user profile (/me)

 - Admin-only: List all users

### 📁 Phase 3: Project & Team Management
 Create Project entity

 - Many-to-Many relation: Users <-> Projects

 - CRUD endpoints for Projects

 - Assign users to a project

 - List user’s projects

 - Only managers can edit projects

### 📌 Phase 4: Task Management
 - Create Task entity with fields: title, description, status, priority, due date

 - Relations: One-to-Many (Project -> Tasks), Many-to-One (User -> Task)

 - Task CRUD endpoints

 - Assign tasks to developers

 - Developer can list and update their tasks

### ⏱️ Phase 5: Time Tracking System
 - Create TimeEntry entity with startTime, endTime, duration, taskId, userId

 - Endpoint: Start timer (store start time)

 - Endpoint: Stop/Pause timer (store end time and calculate duration)

 - Endpoint: Log manual time (with optional comment)

 - Ensure users can't log overlapping time

### 📊 Phase 6: Reporting & Analytics
 - API for weekly report per developer (total hours, tasks done)

 - Project-level report (total hours from all users)

 - Task completion statistics

 - Export reports to CSV or PDF (optional)

### 🛡️ Phase 7: Admin Features
 - View all users with stats

 - Deactivate/reactivate users

 - Force-stop timers running too long

 - System usage metrics (active users, projects, etc.)

### 🧪 Phase 8: Testing
 - Write unit tests for services

 - Write e2e tests for controllers

 - Create a Postman collection for testing manually

### 📦 Phase 9: Final Touches
 - Swagger API docs setup

 - Seed database with sample data using Faker.js

 - Dockerize the application

 - Setup CI/CD (GitHub Actions or similar)

### ✨ Optional Enhancements
 - Add WebSocket for real-time timer/task updates

 - Email notifications (task due soon, timer reminders)

 - Cron jobs for scheduled tasks (e.g., daily reports)

 - GraphQL support for frontend clients

