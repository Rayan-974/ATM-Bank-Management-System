# 🏦 ApexBank — ATM Bank Management System

A high-fidelity, desktop-based Automated Teller Machine (ATM) simulator and core banking management engine. Built using **Java Swing & AWT**, this application integrates with a **MySQL relational database via JDBC** to handle everything from secure multi-stage user onboarding to real-time transactional ledger updates.

## 📋 Table of Contents
- [✨ Core System Features](#-core-system-features)
- [🧱 Architecture & Data Flow](#-architecture--data-flow)
- [🗄️ Relational Database Schema](#️-relational-database-schema)
- [🛠️ Tech Stack & Dependencies](#%EF%B8%8F-tech-stack--dependencies)
- [📁 Project Layout Directory](#-project-layout-directory)
- [🔧 Getting Started](#-getting-started)
- [🙋 Author](#-author)

---

## ✨ Core System Features

* **📟 Immersive ATM Interface:** A realistic physical terminal layout panel managing secure session verification, real-time balance displays, and screen state transitions.
* **📝 Multi-Tier Onboarding Pipeline:** A multi-page wizard collecting demographic details, socio-economic compliance data, and generating systemic unique account tracking, card strings, and secure PIN configurations.
* **💸 Full-Service Transaction Suite:**
  * **Cash Ledger Mutations:** Real-time handling for secure deposits and precise withdrawal checks.
  * **Fast Cash Express:** Quick-click macros to instantly execute standard currency distribution loops.
  * **PIN Self-Service Administration:** Live validation tracking allowing users to update and re-encrypt account access keys instantly.
* **🧾 Automated Auditing:** Live relational database querying to output instant mini-statements and multi-line transaction histories on screen.

---

## 🧱 Architecture & Data Flow

The system strictly decouples its presentation layout elements from structural database operations using a programmatic connector bridge:

```text
       [ User Action ] ──► Submit Button Event
                                │
                                ▼
                 [ Swing / AWT Layout Panels ]
               Validates layout logic & field input
                                │
                                ▼
                 [ JDBC Connection Pipeline ]
                Dispatches secure state commands
                                │
         ┌──────────────────────┴──────────────────────┐
         ▼                                             ▼
 [ Query Modifications ]                       [ Data Fetch Engine ]
 (INSERT / UPDATE)                             (ResultSet Evaluation)
         │                                             │
         ▼                                             ▼
  Updates account records                       Fetches balances, pins,
  & append transaction logs.                   and multi-line history statements.

```

---

## 🗄️ Relational Database Schema

The core operations run on a structured database schema engine labeled `banksystem`. Entity states are mapped across these dedicated operational tables:

| Entity Table | Core Metrics Tracked | Systemic Target Role |
| --- | --- | --- |
| **`signup`** | `formno`, `name`, `email`, `city` | Stores basic personal identity records. |
| **`signuptwo`** | `formno`, `religion`, `income`, `cnic` | Logs socio-economic compliance data. |
| **`signupthree`** | `formno`, `accountType`, `cardnumber`, `pin` | Provisions banking tokens and access variables. |
| **`login`** | `cardnumber`, `pin` | High-speed indexing table for terminal entry checking. |
| **`bank`** | `cardnumber`, `date`, `type`, `amount` | Append-only ledger sheet logging complete cash streams. |

---

## 🛠️ Tech Stack & Dependencies

* **Frontend Engine:** Java Swing & Abstract Window Toolkit (AWT)
* **Storage Layer:** MySQL Server RDBMS
* **Database Driver System:** MySQL Connector/J `9.1.0` (Native Type-4 JDBC Framework)
* **Chronological Utilities:** `JCalendar 1.4` (Ensures cross-platform visual date selection)

---

## 📁 Project Layout Directory

```text
├── src/
│   └── bank/
│       └── management/
│           └── system/
│               ├── Login.java          # Security gate-keeper and card verification screen
│               ├── SignupOne.java       # Personal demographic onboarding module
│               ├── SignupTwo.java       # Socio-economic metric collection layer
│               ├── SignupThree.java     # Card generation, PIN distribution, and submission
│               ├── Conn.java           # Central JDBC instance pool provider
│               └── Transactions.java   # Core ATM transaction selection dashboard
├── lib/
│   ├── mysql-connector-j-9.1.0.jar     # High-speed back-end database connector
│   └── jcalendar-1.4.jar               # UI chronological date-picker utility
├── database/
│   └── bank.sql                        # Master schema table initialization query asset
└── out/                                # Target location for compiled production bytecode

```

---

## 🔧 Getting Started

### 1. Relational Database Setup

1. Ensure your local MySQL server instance is live on port `3306` (via XAMPP, native installer, etc.).
2. Initialize the database schema inside your terminal environment:
```sql
CREATE DATABASE banksystem;

```


3. Load the pre-configured tables mapping script directly to your database:
```bash
mysql -u root -p banksystem < database/bank.sql

```



### 2. Compilation & Execution Lifecycle

#### Command Line Compilation

Compile all native source scripts along your required library classpaths:

```bash
javac -cp "lib/jcalendar-1.4.jar;lib/mysql-connector-j-9.1.0.jar" -d out src/bank/management/system/*.java

```

Launch the primary UI loop entry program:

```bash
java -cp "out;src;lib/jcalendar-1.4.jar;lib/mysql-connector-j-9.1.0.jar" bank.management.system.Login

```

#### Modern IDE Configuration (IntelliJ IDEA / Eclipse)

1. Import this repository folder context directly into your IDE workspace.
2. Under **Project Structure / Build Paths**, add the `.jar` assets inside the `lib/` directory as explicit **Module Libraries**.
3. Right-click `src/bank/management/system/Login.java` and select **Run** (`Shift + F10`).

---

## 🙋 Author

**Rayan Ahmer** 

---

⭐ Star this repository if you found it helpful!
