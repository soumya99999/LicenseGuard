# 📦 License Inventory Management Module – LicenseGuard

## 📘 Overview
The **License Inventory Management** module is a core component of the **LicenseGuard System**, responsible for **storing, managing, and tracking software licenses** purchased by different departments.  
It integrates with procurement records, monitors license availability, and supports downstream modules such as **renewal alerts, license assignment, compliance monitoring, and reporting**.

---

## 🎯 Module Objectives
- Track and store department-wise software license details.  
- Ensure traceability of license origin through procurement record mapping.  
- Maintain quantity metrics for usage and assignment.  
- Provide REST APIs to retrieve license data by ID, department, or procurement record.  

---

## 🧱 Entity: `LicenseInventory`

**Mapped Table:** `license_inventory`

### Fields

| Field Name          | Data Type     | Description                                   |
|---------------------|---------------|-----------------------------------------------|
| `softwareName`      | String        | Name of the software                          |
| `licenseKey`        | String (Unique) | Unique license key assigned to the software   |
| `totalQuantity`     | int           | Total number of licenses purchased            |
| `availableQuantity` | int           | Number of licenses currently available        |
| `purchaseDate`      | LocalDate     | Date when the license was purchased           |
| `expiryDate`        | LocalDate     | Date when the license will expire             |

### Relationships

| Relationship Type | Related Entity     | Join Column      | Description                                   |
|-------------------|-------------------|------------------|-----------------------------------------------|
| `@ManyToOne`      | Department        | `department_id`  | Associates license with a specific department |
| `@ManyToOne`      | ProcurementRecord | `procurement_id` | Links license to its source procurement       |

---

## 🌐 REST API Endpoints

**Base URL:** `/api/licenses`

| Method | Endpoint                | Description                   |
|--------|-------------------------|-------------------------------|
| `POST` | `/`                     | Create a new license record   |
| `GET`  | `/`                     | Retrieve all licenses         |
| `GET`  | `/{id}`                 | Get license by ID             |
| `GET`  | `/department/{deptId}`  | Get licenses by department    |
| `GET`  | `/procurement/{procId}` | Get licenses by procurement   |

---

## 🔄 Dependencies

- **Inputs Required**
  - Valid `department_id`  
  - Valid `procurement_id`  

- **Used By**
  - **Expiry & Renewal Module** → Uses `expiryDate` to trigger alerts  
  - **Assignment Module** → Uses `availableQuantity` for allocation  
  - **Compliance Monitoring** → Checks license usage limits  
  - **Reporting Module** → Generates audit and usage reports  

---

## 🛠️ Technologies Used
- **Backend Framework**: Spring Boot (Java)  
- **ORM**: Hibernate / JPA  
- **Database**: MySQL (or any relational DB)  
- **DTO Layer**: For mapping between Entity and Controller  

---

## 📌 Notes
- All license keys must be **unique**.  
- Department and procurement records must exist before creating a license entry.  
- Date format in POST requests must follow **`yyyy-MM-dd`**.  

---

## 👨‍💻 Developers
**Soumya Ranjan Barik & Nihal Kumar**  
_Module Owners – License Inventory Management, LicenseGuard System_  

---
