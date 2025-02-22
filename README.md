# 🚀 Omni: AI-Powered Social Media Planner & Analytics

### A fully automated social media scheduling & analytics platform powered by AI.

---

## 📌 Features
✅ **Social Media Analytics Dashboard** – Track real-time analytics from **Facebook, Instagram, LinkedIn, Twitter, TikTok, and YouTube** with **follower growth, engagement, and impressions**.  

✅ **AI-Powered Caption Generator** – Uses **OpenAI API** to generate captions and hashtag suggestions, customizable by **tone, length, and platform**.  

✅ **Automated Post Scheduling** – Schedule posts across multiple platforms with a single click. Posts are automatically published via **background jobs**.  

✅ **Team Management & Subscription Plans** – Invite team members, manage permissions, and enforce limits based on **subscription plans (Minimal, Team, Enterprise)**.  

✅ **Auto-Deployment & CI/CD** – Backend deploys via **Firebase Functions**, frontend deploys via **Vercel**, and GitHub Actions automate **testing & deployment**.  

---

## 📌 Tech Stack
- **Backend:** Node.js / Python (FastAPI)  
- **Database:** Firebase Firestore / PostgreSQL  
- **Authentication:** OAuth 2.0 (Google, Facebook, LinkedIn, Twitter)  
- **Frontend:** React.js (Next.js)  
- **UI Styling:** Tailwind CSS  
- **State Management:** Redux / Context API  
- **Charts & Analytics:** Chart.js / Recharts  
- **AI Integration:** OpenAI API  
- **Deployment:** Firebase Functions, Vercel  

---

## 📌 Repository Structure
/omni ├── /backend # Devin handles this │ ├── /api # API endpoints │ ├── /auth # Authentication │ ├── /models # Database models │ ├── /tasks # Scheduled jobs │ ├── /utils # Helper functions │ ├── index.js # Main backend entry │ ├── package.json │ ├── /frontend # Cursor handles this │ ├── /components # React/Vue UI components │ ├── /pages # Page-level UI │ ├── /services # API calls to backend │ ├── /hooks # Custom React hooks │ ├── /styles # Tailwind CSS styles │ ├── index.tsx # Frontend entry │ ├── package.json │ ├── /docs # Documentation & Changelog │ ├── CHANGELOG.md │ ├── README.md │ ├── .github # GitHub Actions │ ├── workflows │ ├── .gitignore ├── README.md


---

## 📌 Setup & Installation
### **1️⃣ Clone the Repository**
Run the following in your terminal:  
`git clone https://github.com/YOUR_GITHUB_USERNAME/omni.git`  
`cd omni`  

### **2️⃣ Install Backend Dependencies**
`cd backend`  
`npm install`  

### **3️⃣ Install Frontend Dependencies**
`cd ../frontend`  
`npm install`  

### **4️⃣ Set Up Environment Variables**
Create a `.env` file in both `backend/` and `frontend/`:

#### 🔹 Backend (`backend/.env`)

Firebase
FIREBASE_API_KEY=your_api_key 
FIREBASE_AUTH_DOMAIN=your_auth_domain 
FIREBASE_PROJECT_ID=your_project_id

OpenAI API Key
OPENAI_API_KEY=your_openai_key

OAuth Credentials
GOOGLE_CLIENT_ID=your_google_client_id 
GOOGLE_CLIENT_SECRET=your_google_client_secret

shell
Copy
Edit

#### 🔹 Frontend (`frontend/.env`)
NEXT_PUBLIC_API_URL=http://localhost:5000

markdown
Copy
Edit

### **5️⃣ Run the Application**
#### 🔹 Start Backend  
`cd backend`  
`npm start`  

#### 🔹 Start Frontend  
`cd ../frontend`  
`npm run dev`  

🚀 **Now, open `http://localhost:3000` to start using Omni!** 🎉  

---

## 📌 Development Workflow
### **1️⃣ Create a Feature Branch**
`git checkout -b feature/your-feature-name`  

### **2️⃣ Commit Changes**
`git commit -m "Added new feature"`  

### **3️⃣ Push to GitHub & Create Pull Request**
`git push origin feature/your-feature-name`  

✅ **All PRs must follow our guidelines in `.devinrules` & `.cursorrules`.**  

---

## 📌 Continuous Integration & Deployment
✅ **Auto-Deploy to Firebase (Backend) & Vercel (Frontend)**  
- Merging into `main` triggers **GitHub Actions** for deployment.  
- **Backend** deploys via **Firebase Functions**.  
- **Frontend** deploys via **Vercel**.  

✅ **GitHub Actions for CI/CD**
- **Code Testing** – Runs tests before merging a PR  
- **Deployment** – Auto-deploys when PR is merged to `main`  
- **Docs Enforcement** – Prevents merges without documentation updates  

---

## 📌 GitHub Action Workflows
### 🔹 Backend Deployment (`.github/workflows/deploy-backend.yml`)
name: Deploy Backend on: push: branches: - main jobs: deploy: runs-on: ubuntu-latest steps: - name: Checkout repository uses: actions/checkout@v3 - name: Deploy to Firebase run: firebase deploy --only functions

shell
Copy
Edit

### 🔹 Frontend Deployment (`.github/workflows/deploy-frontend.yml`)
name: Deploy Frontend on: push: branches: - main jobs: deploy: runs-on: ubuntu-latest steps: - name: Checkout repository uses: actions/checkout@v3 - name: Deploy to Vercel run: vercel --prod
