# ATM Bank Management System

A desktop-based ATM Bank Management System built with Java Swing, AWT, JDBC, and MySQL. It features a complete banking flow including account registration, deposits, withdrawals, PIN changes, balance inquiry, and transaction receipts.

## Features

- **ATM Screen**: Simulates a real ATM layout and menu.
- **Card Login**: Secure login with simulated Card Number and PIN.
- **User Registration**: A multi-page sign-up flow capturing personal information, CNIC number, contact details, account type preferences, and ATM card generation.
- **Transactions**:
  - Cash Deposit
  - Cash Withdrawal
  - Fast Cash (quick withdrawals)
  - Balance Inquiry
  - PIN Change
  - Mini Statement (transaction history)

## Technologies Used

- **Frontend**: Java Swing & AWT (GUI components)
- **Database**: MySQL Server
- **Database Driver**: MySQL Connector/J 9.1.0
- **Calendar Library**: JCalendar 1.4 (for date picking)

## Getting Started

### 1. Database Setup

1. Make sure MySQL is running on your machine (e.g., via XAMPP or native installer) on port `3306`.
2. Import the database schema:
   - Create a database named `banksystem`.
   - Run the tables initialization script (`bank.sql` file provided in the repository).

### 2. Compilation and Execution

#### Command Line

Compile all Java source files with the required libraries:
```bash
javac -cp "lib/jcalendar-1.4.jar;lib/mysql-connector-j-9.1.0.jar" -d out src/bank/management/system/*.java
```

Run the application:
```bash
java -cp "out;src;lib/jcalendar-1.4.jar;lib/mysql-connector-j-9.1.0.jar" bank.management.system.Login
```
🙋 Author
Rayan Ahmer 

⭐ Star this repository if you found it helpful!

#### IntelliJ IDEA / Eclipse

1. Open the project folder in your IDE.
2. The project libraries are configured in the `.idea` folder and will automatically load the dependencies from the `lib` folder.
3. Run the main class: `bank.management.system.Login`.
