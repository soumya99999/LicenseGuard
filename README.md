# 🎯 LicenseGuard – License Inventory Frontend

## 📖 Introduction  
The **LicenseGuard License Inventory Frontend** is a modern web application for managing software license records across departments. It provides an intuitive interface to **create, view, filter, and track licenses** tied to procurement data.  

Built with a scalable tech stack, it integrates seamlessly with the LicenseGuard backend via REST APIs, enabling **real-time synchronization** of license information.  

---

## ✨ Features  
- ➕ Add new software license entries using an interactive form  
- 📑 View all licenses in a **paginated and sortable table**  
- 🔎 Filter licenses by **Department ID** or **Procurement Record ID**  
- 📅 Track purchase and expiry dates for compliance and renewals  
- 🔄 Real-time data updates through REST API integration  

---

## 🛠️ Tech Stack  

| Layer               | Technology |
|---------------------|------------|
| **Framework**       | React.js / Next.js |
| **HTTP Client**     | Axios / Fetch API |
| **Styling**         | Tailwind CSS / Bootstrap / Material UI |
| **Routing**         | React Router (if applicable) |
| **State Management**| React Hooks / Zustand / Redux Toolkit |

---

## 🌐 API Endpoints  

The frontend interacts with the backend service via the following endpoints:  

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/licenses` | Create a new license entry |
| `GET`  | `/api/licenses` | Retrieve all license records |
| `GET`  | `/api/licenses/{id}` | Retrieve license by ID |
| `GET`  | `/api/licenses/department/{deptId}` | Retrieve licenses by Department |
| `GET`  | `/api/licenses/procurement/{procId}` | Retrieve licenses by Procurement Record |

---

## 🚀 Getting Started  

### 1️⃣ Clone the Repository  
```bash
git clone https://github.com/soumya99999/LicenseGuard.git
cd LicenseGuard
