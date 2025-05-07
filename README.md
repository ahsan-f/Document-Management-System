# AI-Powered Document Management System (DMS)

This project is an intelligent, end-to-end Document Management System that integrates AI agents with SharePoint to automate document ingestion, classification, and lifecycle management. It is built using modern web technologies, local AI models, and robust Microsoft authentication protocols.

---

## Key Features

- Document upload and browsing through a modern web interface
- Automated metadata extraction using NLP
- OCR support for scanned documents and images
- AI-based duplicate document detection
- Document summarization using local LLMs
- Integration with SharePoint for version control and compliance
- Role-Based Access Control (RBAC) via Microsoft SSO
- Workflow automation for approvals, notifications, and tagging

---

## System Architecture Overview

```
Frontend (React.js)
   ↕
Backend API (FastAPI)
   ↕
AI Workflow Agents (LangGraph / CrewAI)
   ↕
SharePoint API (Microsoft Graph)
```

---

## Components

### 1. Frontend (React.js)
- Document upload and metadata preview
- Dashboard with role-specific views
- Microsoft SSO integration via MSAL.js

### 2. Backend (FastAPI)
- Handles API endpoints for upload, status, and retrieval
- Manages AI agent orchestration
- Pushes final results to SharePoint
- Handles token validation and RBAC logic

### 3. AI Agent Workflow
| Agent                  | Description                                      |
|------------------------|--------------------------------------------------|
| **OCR Agent**          | Converts scanned PDFs/images to text             |
| **Metadata Agent**     | Extracts title, date, tags, type using NLP       |
| **Duplicate Agent**    | Compares vectors to detect similar documents     |
| **Summarization Agent**| Condenses content for quick review               |
| **Workflow Trigger**   | Initiates approval/review routing                |

Frameworks: `LangGraph`, `CrewAI`, `FAISS`, `Tesseract`, `Transformers`

### 4. SharePoint Integration
- Uses Microsoft Graph API
- Uploads documents and metadata
- Manages folder structure, permissions, and versioning

### 5. Authentication & RBAC
- Microsoft Single Sign-On (SSO)
- MSAL.js frontend authentication
- Role-based permission checks via SharePoint groups

---

## Getting Started

### Prerequisites
- Node.js & npm
- Python 3.9+
- Microsoft 365 Tenant with SharePoint access
- Azure App Registration for MSAL & Graph API
- Docker (optional for deployment)

### Setup

#### Frontend
```bash
cd frontend
npm install
npm start
```

#### Backend
```bash
cd backend
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
uvicorn main:app --reload
```

#### Environment Variables
- `REACT_APP_CLIENT_ID`
- `REACT_APP_TENANT_ID`
- `GRAPH_API_TOKEN`
- `SHAREPOINT_SITE_ID`
- `SHAREPOINT_DRIVE_ID`

---

## Security

- OAuth 2.0 and OpenID Connect via MSAL
- Role checks before upload, view, or edit actions
- Audit logs for all critical events (optional)

---

## Deployment

Recommended: Azure App Services + Azure AD + Azure Functions

Optional: Dockerize backend and deploy on VM or Kubernetes

---

## Local LLM Support

- LLMs like `Mistral`, `Phi-3`, `LLaMA` supported via Transformers
- Optionally integrate `llama-cpp` or `ollama` for lightweight local inference

---

## License
MIT License. See `LICENSE.md` for details. 

---

## Contributing
PRs are welcome. Please open an issue before proposing major changes.

---

## Future Enhancements

- Document comparison and diffing
- Chat-with-documents using RAG
- Notification system via Teams or Email
- Advanced analytics and reporting

---

## Contact

For questions or further information, please contact Adon Mathew at apm1@systra.info.

---