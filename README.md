# 🧠 RAG-QNA App – Full Stack Setup with Docker

This project is a full-stack RAG (Retrieval-Augmented Generation) application, composed of:

- 🚀 FastAPI backend (Python)
- 🌐 NestJS backend (Node.js)
- 💻 React frontend (Vite)
- 🐘 PostgreSQL with pgvector

<img width="1679" alt="image" src="https://github.com/user-attachments/assets/40257a6a-9720-480a-9964-ffeabb4a21b1" />
<img width="1673" alt="image" src="https://github.com/user-attachments/assets/3778331c-e7e0-4aab-b422-8f8d8f4a0f91" />
<img width="1679" alt="image" src="https://github.com/user-attachments/assets/4c3d6535-b4e0-43dd-ab15-69f495b6e452" />
<img width="1679" alt="image" src="https://github.com/user-attachments/assets/f84f0027-411c-4a59-9d90-265ae3716893" />
<img width="1679" alt="image" src="https://github.com/user-attachments/assets/a45820d5-4561-4881-b635-09be3ee017a0" />
<img width="1679" alt="image" src="https://github.com/user-attachments/assets/b3c1878b-24b0-4ac0-9757-d188579be454" />


## System Architechture
<img width="536" alt="image" src="https://github.com/user-attachments/assets/c36c58ae-3ce2-4809-88db-37c630f7c423" />


---
### Everything is containerized using **Docker**, and can be run locally using a single command.

## 📁 Project Structure

```
RAG-QNA-SONIKA/
├── docker-compose.yml
├── rag-fastapi-backend/
│ ├── Dockerfile
│ ├── main.py
│ └── requirements.txt
├── rag-nest-backend/
│ ├── Dockerfile
│ ├── src/
│ └── package.json
├── rag-frontend-react-vite/
│ ├── Dockerfile
│ ├── src/
│ └── package.json
├── database/
│ └── init.sql (optional)
└── README.md
```






---

## ⚙️ Prerequisites

Make sure the following are installed on your system:

- [Docker](https://www.docker.com/products/docker-desktop)
- [Docker Compose](https://docs.docker.com/compose/install/) (usually comes with Docker Desktop)

---

## 🚀 Getting Started (One Command Setup)

From the root of the project, run:

```bash
./build.sh
```

---

## 🌐 Service URLs & Access Points

| Service | Description | URL | Health Check |
|---------|-------------|-----|--------------|
| **Frontend** | React + Vite SPA | [http://localhost:5173](http://localhost:5173) | ✅ UI loads |
| **FastAPI** | Python ML Backend | [http://localhost:8000](http://localhost:8000) | [/health](http://localhost:8000/health) |
| **NestJS** | Node.js API Backend | [http://localhost:3000](http://localhost:3000) | [/health](http://localhost:3000/health) |
| **PostgreSQL** | Vector Database | `localhost:5455` | Connection test |
| **API Docs** | FastAPI Swagger | [http://localhost:8000/docs](http://localhost:8000/docs) | Interactive API |
| **NestJS Docs** | NestJS Swagger | [http://localhost:3000/api](http://localhost:3000/api) | API Documentation |

### Database Connection Details
```
Host: localhost
Port: 5455
Database: rag_db
Username: rag_user
Password: rag_pass
Connection URL: postgresql://rag_user:rag_pass@localhost:5455/rag_db
```

---

## 🛠️ Development Setup

```bash
# 1. Clone the repository
git clone https://github.com/sabirAIE/rag-based-q-a.git

# 2. Move into the project directory
cd rag-based-q-a

# 3. (Optional) If any subfolders have their own .git folders, remove them
rm -rf rag-nest-backend/.git
rm -rf rag-fastapi-backend/.git
rm -rf rag-frontend-react-vite/.git

# 4. Remove any existing git history and reinitialize (if needed)
rm -rf .git
git init
git remote add origin https://github.com/sabirAIE/rag-based-q-a.git

# 5. Add and commit project files
git add .
git commit -m "Initial commit - cleaned nested git histories"

# 6. Push to GitHub (force push if needed)
git branch -M main
git push --force -u origin main

# 7. Build and run all services with Docker
docker-compose up --build

# 8. Access the app locally:
# Frontend    -> http://localhost:5173
# FastAPI     -> http://localhost:8000
# NestJS      -> http://localhost:3000
# Postgres DB -> localhost:5455 (user: rag_user, pass: rag_pass, db: rag_db)
```
---
