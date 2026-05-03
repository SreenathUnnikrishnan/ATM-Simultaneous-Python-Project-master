# 🏦 Python Command-Line ATM Simulator

![Python Version](https://img.shields.io/badge/python-3.x-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)

> A highly interactive, secure, and user-friendly Automated Teller Machine (ATM) simulator built entirely in Python. 

---

## 📑 Table of Contents
1. [About the Project](#-about-the-project)
2. [Key Features](#-key-features)
3. [Technical Architecture](#-technical-architecture)
4. [Getting Started](#-getting-started)
5. [Usage & Test Accounts](#-usage--test-accounts)
6. [Roadmap & Future Enhancements](#-roadmap--future-enhancements)
7. [Contributing](#-contributing)
8. [License](#-license)

---

## 📖 About The Project

This project is a terminal-based replica of a real-world ATM interface. It was designed to demonstrate fundamental programming concepts such as continuous state loops, control flow, secure user input, and list management. It serves as an excellent foundational project for understanding how backend logic connects to user-facing menus.

### Built With
* **Python 3.x** - The core programming language.
* **`getpass`** - Standard library module used to securely mask PIN inputs.
* **`os`** - Standard library module for interacting with the operating system (e.g., clearing the terminal screen).

---

## ✨ Key Features

This simulator mimics core banking functionalities with strict validation and error handling:

* 🔒 **Secure Authentication System**
  * Verifies usernames against an internal database.
  * Masks PIN input to prevent shoulder-surfing.
  * Implements a **3-strike lockout policy**—failing to enter the correct PIN 3 times will lock the session and exit the program.
* 💰 **Account Statements**
  * Instantly retrieves and formats the current user's available balance.
* 🏧 **Withdrawal Logic**
  * Enforces strict ATM dispensing rules (e.g., funds must be withdrawn in multiples of €10).
  * Prevents overdrafts with "Insufficient Balance" checks.
* 🏦 **Lodgement (Deposits)**
  * Allows users to deposit funds.
  * Validates that inputted cash matches valid note denominations (multiples of €10).
* 🔑 **Security Management (Change PIN)**
  * Users can securely update their PIN.
  * Requires the new PIN to be exactly 4 digits, different from the old PIN, and verified through a double-entry confirmation step.

---

## 🏗️ Technical Architecture

Currently, the application relies on an **in-memory data structure** using parallel lists. 
* `users`: Stores valid account names.
* `pins`: Stores the corresponding 4-digit PIN codes.
* `amounts`: Stores the corresponding account balances.

The application runs inside an infinite `while True` loop, presenting the main menu until the user explicitly chooses the `Quit (Q)` option or triggers a security lockout.

---

## 🚀 Getting Started

To get a local copy up and running, follow these simple steps.

### Prerequisites
You only need Python installed on your machine. You can verify your installation by opening a terminal and typing:
```bash
python --version
```

### Installation
1. Clone the repository to your local machine:
   ```bash
   git clone https://github.com/yourusername/atm-simulator.git
   ```
2. Navigate to the project directory:
   ```bash
   cd atm-simulator
   ```
3. Run the application:
   ```bash
   python atm_fixed.py
   ```

---

## 🕹️ Usage & Test Accounts

When you launch the program, you will be prompted to enter a username and a PIN. Use any of the pre-configured accounts below:

| Username | PIN  | Starting Balance |
| :--- | :--- | :--- |
| `user1` | `1234` | €1,000 |
| `user2`| `2222` | €2,000 |
| `user3`| `3333` | €3,000 |

### Example Session Flow:
1. **ENTER USER NAME:** `user1`
2. **PLEASE ENTER PIN:** `****` *(type 1234)*
3. **Select `S`** to view your €1000 balance.
4. **Select `W`**, type `40`, and see your balance drop to €960.
5. **Select `Q`** to safely exit the system.

---

## 🗺️ Roadmap & Future Enhancements

While fully functional, there are several ways this project can be expanded in the future:
- [ ] **Refactor Data Storage:** Replace parallel lists with Python Dictionaries or a JSON file for cleaner data management.
- [ ] **Transaction History:** Create a list that logs every deposit and withdrawal, printable via a new menu option.
- [ ] **Database Integration:** Implement `SQLite3` to save balances persistently across different sessions.
- [ ] **Object-Oriented Programming (OOP):** Rewrite the code using `User` and `Bank` classes.

---

## 🤝 Contributing

Contributions make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/NewBankFeature`)
3. Commit your Changes (`git commit -m 'Add some NewBankFeature'`)
4. Push to the Branch (`git push origin feature/NewBankFeature`)
5. Open a Pull Request

---

## 📝 License

Distributed under the MIT License. See `LICENSE` for more information.
