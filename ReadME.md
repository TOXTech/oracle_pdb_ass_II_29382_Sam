# Oracle Pluggable Database Assignment II

**Student Name:** IRUMVA Sam Blessing  
**Student ID:** 29382

---

## 📋 Assignment Overview

This repository contains the complete implementation of Oracle Pluggable Database (PDB) management:

1. ✅ Creating persistent PDB with application user
2. ✅ Demonstrating PDB lifecycle (creation and deletion)
3. ✅ Configuring and accessing Oracle Enterprise Manager

---

## 🖥️ Environment Configuration

### System Information

| Component            | Details             |
| -------------------- | ------------------- |
| **Operating System** | Windows 11 / Linux  |
| **Oracle Version**   | Oracle Database 21c |
| **CDB Name**         | ORCL                |
| **OEM HTTPS Port**   | 5500                |

---

## ✅ Task 1: Persistent PDB Creation

### PDB Details

- **PDB Name:** `sa_pdb_29382`
- **Application User:** `sam_plsqlauca_29382`
- **Status:** OPEN (READ WRITE)
- **State:** SAVED

### Implementation

Created PDB from seed:

```sql
CREATE PLUGGABLE DATABASE sa_pdb_29382
    ADMIN USER pdbadmin IDENTIFIED BY AdminPass123
    FILE_NAME_CONVERT = (...);
```

Opened and saved state:

```sql
ALTER PLUGGABLE DATABASE sa_pdb_29382 OPEN;
ALTER PLUGGABLE DATABASE sa_pdb_29382 SAVE STATE;
```

Created user:

```sql
CREATE USER sam_plsqlauca_29382 IDENTIFIED BY plsql;
GRANT ALL PRIVILEGES TO sam_plsqlauca_29382;
```

### Evidence

![PDB Creation](assets/01_pdb_creation_success.png)
![User Created](assets/05_user_created.png)
![User Test](assets/07_test_successful.png)

---

## 🔄 Task 2: PDB Lifecycle Management

### Temporary PDB

- **Name:** `sa_to_delete_pdb_29382`
- **Purpose:** Demonstrate creation and deletion

### Process

1. Created temporary PDB
2. Verified existence with timestamp
3. Closed PDB gracefully
4. Dropped with datafiles
5. Confirmed removal

### Evidence

![PDB Created](assets/08_temp_pdb_exists.png)
![PDB Dropped](assets/10_pdb_dropped.png)
![Deletion Confirmed](assets/11_pdb_deleted_confirmed.png)

---

## 🖥️ Task 3: Oracle Enterprise Manager

### Configuration

- **Access URL:** https://localhost:5500/em
- **Port:** 5500
- **Login:** sys (as SYSDBA)

### Evidence

![OEM Dashboard](assets/13_oem_dashboard_main.png)

---
