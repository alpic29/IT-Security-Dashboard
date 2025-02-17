# IT Security Dashboard for User & System Monitoring

## 📌 Project Overview
An **open-source security monitoring dashboard** that tracks user activity, system logs, and security alerts. This tool helps **IT administrators detect and prevent security threats** by leveraging **real-time monitoring, AI-powered anomaly detection, and automated alerts**.

## 🚀 Features
- **Live User Activity Tracking** 📊  
  Monitor login attempts, IP addresses, and suspicious access patterns.
- **AI-Powered Anomaly Detection** 🤖  
  Detects unusual login behaviors, multiple failed access attempts, and abnormal API usage.
- **Real-Time Alerts** 🚨  
  Notifies admins via **email, Slack, or Discord** for security events.
- **Role-Based Access Control (RBAC)** 🔐  
  Assign different access levels to admins, users, and security personnel.
- **Audit Logging for Compliance** 📜  
  Keeps detailed logs of all system events and admin actions.
- **API Integrations** 🔌  
  Supports **Microsoft Graph API, webhook notifications, and RESTful API** for external tools.

## 🛠 Tech Stack
| Component      | Technology |
|---------------|------------|
| **Frontend**  | React.js (Next.js) |
| **Backend**   | FastAPI (Python) |
| **Database**  | MongoDB Atlas |
| **Authentication** | JWT / OAuth2 (Google, Microsoft) |
| **AI Features** | TensorFlow / PyTorch (Anomaly Detection) |
| **Deployment** | Docker & Kubernetes (optional) |

## 📥 Installation Guide
### Prerequisites
- **Python 3.9+** & **pip**
- **MongoDB Atlas** account
- **GitHub account** (for contribution)

### 🚀 Setup Instructions
#### Backend Setup (FastAPI)
```bash
# Clone the repository
git clone https://github.com/your-username/it-security-dashboard.git
cd it-security-dashboard/backend

# Install dependencies
pip install -r requirements.txt

# Run the backend
uvicorn main:app --reload
```

#### Frontend Setup (React.js Example)
```bash
cd ../frontend
npm install
npm run dev
```

The app will be available at **http://localhost:3000**.

## ⚙️ Setting Up MongoDB Atlas
1. **Create an Account & Cluster**
   - Sign up at [MongoDB Atlas](https://www.mongodb.com/atlas)
   - Create a new **free-tier cluster**
   - Select a cloud provider & region

2. **Configure Database Access**
   - Go to **Database Access** and create a new user
   - Set a strong password and **save it securely**
   - Assign the role **"Read and Write to Any Database"**

3. **Allow Network Access**
   - Go to **Network Access** and click **Add IP Address**
   - Choose **"Allow Access from Anywhere"** (or specify your IP for security)

4. **Connect to Your Database**
   - Click **Connect** → **Connect your application**
   - Copy the **MongoDB connection string**
   - Replace `<your-password>` in the string with your actual database password

5. **Update Your FastAPI App**
   - In your `config.py` or `.env` file, add:
     ```bash
     MONGO_URI=mongodb+srv://your-username:<your-password>@cluster.mongodb.net/?retryWrites=true&w=majority
     ```
   - Install MongoDB driver for Python:
     ```bash
     pip install pymongo
     ```
   - Connect to MongoDB in FastAPI:
     ```python
     from pymongo import MongoClient
     import os

     client = MongoClient(os.getenv("MONGO_URI"))
     db = client["security_dashboard"]
     users_collection = db["users_activity"]
     ```

## 🤝 Contributing
Contributions are welcome! Follow these steps:
1. Fork the repository.
2. Create a new branch (`feature/new-feature`).
3. Commit your changes and push to your fork.
4. Submit a pull request.

## 📜 License
This project is open-source under the **MIT License**.
