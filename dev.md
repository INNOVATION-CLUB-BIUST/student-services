# 📌 Project Development Guide

## **📂 Project Structure Overview**
This project is structured to support **modular development, scalability, and maintainability**.

### **🌍 Root Directory**
```
project-root/
│-- backend/                  # FastAPI backend
│   ├── app/                  # Core application files
│   │   ├── api/              # API routes
│   │   ├── core/             # Config, database, security
│   │   ├── models/           # Database models
│   │   ├── schemas/          # Pydantic schemas
│   │   ├── services/         # Business logic
│   │   ├── tests/            # Unit tests
│   │   ├── app.py   
|   ├── main.py               # Entry point
│   ├── Dockerfile            # Docker configuration
│   ├── requirements.txt      # Dependencies
│-- frontend/                 # React frontend
│   ├── src/                  # Source code
│   │   ├── components/       # Reusable UI components
│   │   ├── pages/            # Main page components
│   │   ├── services/         # API communication
│   │   ├── store/            # State management (if applicable)
│   ├── package.json          # Dependencies
│-- .gitignore                # Git ignore rules
│-- README.md                 # Project documentation
```

---

## **📌 Backend Folder Breakdown**

### **`api/`**
Contains FastAPI **route definitions** for different services.
```
api/
├── v1/
│   ├── routes/
│   │   ├── auth.py           # Authentication routes
│   │   ├── clinic.py         # Clinic booking routes
│   │   ├── timetable.py      # Timetable automation routes
│   │   ├── maintenance.py    # Maintenance reporting routes
```

### **`core/`**
Handles **global configurations, database connection, and security**.
```
core/
├── config.py       # Environment variables (DB URI, JWT secret, etc.)
├── database.py     # MongoDB connection setup
├── security.py     # Password hashing & JWT authentication
```

### **`models/`**
Defines MongoDB **database models** using Pydantic.

### **`schemas/`**
Defines Pydantic **request & response schemas** for validation.

### **`services/`**
Contains business logic to separate concerns from API routes.

### **`tests/`**
Contains unit tests for different modules.

---

## **📌 Frontend Folder Breakdown**

### **`components/`**
Reusable UI elements (buttons, forms, modals).

### **`pages/`**
Main application views (Dashboard, Login, Booking, etc.).

### **`services/`**
Handles API requests and data fetching using Axios or Fetch.

### **`store/`**
Global state management (if using Redux/Zustand/Context API).

---

# 🚀 Version Control (Git) Workflow

To maintain a **clean and structured repository**, follow this **Git branching strategy**.

## **🔹 Branch Naming Conventions**
| Type       | Naming Format          | Example               |
|------------|----------------------|-----------------------|
| **Main**   | `main`                | `main`                |
| **Development** | `develop`          | `develop`             |
| **Feature** | `feature/<name>`      | `feature/clinic-booking` |
| **Bug Fix** | `fix/<name>`          | `fix/login-redirect`  |
| **Hotfix**  | `hotfix/<name>`       | `hotfix/security-bug` |

## **🔹 Git Workflow**

### **1️⃣ Cloning the Repository**
```
git clone https://github.com/your-repo.git
cd project-root
```

### **2️⃣ Setting Up the Main and Development Branches**
```
git checkout -b develop
```

### **3️⃣ Creating a Feature Branch**
```
git checkout develop
# Create a new branch for a feature
git checkout -b feature/clinic-booking
```

### **4️⃣ Committing Changes**
```
git add .
git commit -m "Added clinic booking API routes"
```

### **5️⃣ Pushing the Feature Branch**
```
git push origin feature/clinic-booking
```

### **6️⃣ Creating a Pull Request (PR)**
- Go to GitHub/GitLab and open a **Pull Request (PR)** from `feature/clinic-booking` → `develop`.
- Request code review and merge after approval.

### **7️⃣ Fixing Bugs**
Create a bug fix branch from `develop`:
```
git checkout develop
git checkout -b fix/login-redirect
```
After fixing the issue, push and create a PR.

### **8️⃣ Deploying Changes**
Once features are tested and merged into `develop`, merge them into `main` for deployment.
```
git checkout main
git merge develop
git push origin main
```

---

# 🔥 Best Practices
✅ **Keep PRs Small** – Focus on one feature/fix per PR.
✅ **Use Descriptive Commit Messages** – Example: `Added JWT authentication to backend`
✅ **Run Tests Before Pushing** – Ensure nothing is broken.
✅ **Always Pull Latest Changes Before Working** – Avoid merge conflicts.

---

This guide ensures **efficient collaboration** and maintains **clean, scalable code**. 🚀

