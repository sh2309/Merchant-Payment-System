# Merchant Payment System Using Blockchain

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python\&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-Web_Framework-black?logo=flask\&logoColor=white)
![Web3.py](https://img.shields.io/badge/Web3.py-Ethereum-3C3C3D?logo=ethereum\&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-Database-003B57?logo=sqlite\&logoColor=white)
![Ganache](https://img.shields.io/badge/Ganache-Local_Blockchain-E4A663?logo=truffle\&logoColor=white)

A blockchain-based payment application built with Python, Flask, Web3.py, and Ganache to demonstrate Ethereum transactions, wallet integration, QR-code-based payments, and balance tracking.

---

## Table of Contents

* [Overview](#overview)
* [Key Features](#key-features)
* [Technology Stack](#technology-stack)
* [System Architecture](#system-architecture)
* [Getting Started](#getting-started)
* [Usage Workflow](#usage-workflow)
* [Project Structure](#project-structure)
* [Security Considerations](#security-considerations)
* [Future Enhancements](#future-enhancements)
* [License](#license)

## Overview

The **Merchant Payment System** demonstrates how blockchain technology can be integrated into a web-based payment application. Users can register, log in, access wallet information, send and receive ETH, and view their wallet balances through a Flask-powered interface.

The application connects to a local Ethereum blockchain running on Ganache. Web3.py handles blockchain interactions, while SQLite stores application data.

This project explores blockchain-based payment workflows, Ethereum wallet integration, and QR-code-based payment collection in a local development environment.

## Key Features

* **User Authentication:** Registration and login using username and password.
* **Ethereum Wallet Integration:** Associates user accounts with Ethereum wallet addresses from Ganache.
* **ETH Transfers:** Sends Ethereum through signed blockchain transactions.
* **QR Code Generation:** Generates QR codes containing wallet addresses to simplify payment collection.
* **Wallet Balance Tracking:** Retrieves ETH balances from the connected blockchain.
* **Transaction Hash Display:** Displays the transaction hash returned after a transaction is submitted successfully.
* **Input Validation and Error Handling:** Supports handling invalid wallet addresses, insufficient balances, and transaction failures, where implemented.
* **Local Blockchain Testing:** Uses Ganache accounts and test ETH for development and experimentation.

## Technology Stack

| Component              | Technology        |
| ---------------------- | ----------------- |
| Programming Language   | Python            |
| Web Framework          | Flask             |
| Blockchain Integration | Web3.py           |
| Blockchain Network     | Ganache           |
| Database               | SQLite3           |
| Frontend               | HTML, CSS, Jinja2 |
| QR Code Generation     | qrcode            |
| Image Processing       | OpenCV (cv2)      |

## System Architecture

The application consists of four main components:

1. **Frontend:** HTML and CSS pages rendered using Flask and Jinja2 templates.
2. **Backend:** Flask routes handle authentication, payment requests, and application logic.
3. **Database:** SQLite stores user and application records.
4. **Blockchain Layer:** Web3.py connects to Ganache to retrieve wallet balances and submit Ethereum transactions.

### Payment Flow

1. The user logs in and selects a payment function.
2. The application receives the recipient's wallet address and payment amount.
3. The application validates the transaction inputs.
4. The transaction is signed using the sender's private key.
5. Web3.py submits the signed transaction to Ganache.
6. The application displays the returned transaction hash.

A transaction hash identifies a transaction, but it does not by itself prove that the transaction has been successfully mined or confirmed.

## Getting Started

Follow these steps to run the application locally.

### Prerequisites

Install the following:

* Python 3.x
* Git
* Ganache
* pip

### 1. Clone the Repository

```bash
git clone https://github.com/sh2309/Merchant-Payment-System.git
cd Merchant-Payment-System
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

Activate the environment on Windows:

```bash
venv\Scripts\activate
```

On macOS or Linux:

```bash
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install flask web3 qrcode opencv-python
```

If a `requirements.txt` file is available in the repository, you can install the dependencies using:

```bash
pip install -r requirements.txt
```

### 4. Start Ganache

1. Open Ganache.

2. Start a Quickstart workspace.

3. Confirm that the RPC endpoint matches the configuration in your application. A common local endpoint is:

   ```text
   http://127.0.0.1:7545
   ```

4. Use the test accounts and test ETH provided by Ganache.

If your application uses a different port or RPC endpoint, update the relevant configuration before running it.

### 5. Initialize the Database

Run the database initialization script:

```bash
python init_db.py
```

This script should create the SQLite database and required tables.

### 6. Run the Application

```bash
python app.py
```

Open your browser and visit:

```text
http://localhost:5002
```

If the application uses a different port, check the configuration in `app.py`.

## Usage Workflow

### 1. Create an Account

Register using the details requested by the application, including your username, password, and Ethereum wallet information.

### 2. Log In

Use your registered credentials to access the application.

### 3. View Your Dashboard

Access the dashboard to view your wallet balance and available payment functions.

### 4. Receive Payments

Generate a QR code containing your Ethereum wallet address and share it with the payer.

### 5. Send Payments

Enter the recipient's wallet address and the amount of ETH to transfer. The application signs and broadcasts the transaction to the configured Ganache network.

### 6. Check Transaction Details

Review the transaction hash returned by the application. Use Ganache to inspect the transaction and verify its status.

## Project Structure

```text
Merchant-Payment-System/
│
├── app.py              # Main Flask application
├── db_conns.py         # Database connection and queries
├── init_db.py          # Database initialization
├── qr_gen.py           # QR code generation logic
├── user.db             # Local SQLite database, if generated
├── static/             # CSS and generated QR images
└── templates/          # HTML and Jinja2 templates
```

The structure above reflects the files described for this project. Confirm the actual repository contents before updating filenames or adding new files.

## Security Considerations

This project is intended for educational and local development use. It is **not a production-ready payment system**.

* **Private Key Protection:** Never commit wallet private keys to GitHub or use real wallet keys for testing. Use Ganache test accounts.
* **Password Security:** Passwords should be stored using an appropriate password-hashing algorithm rather than plaintext.
* **Input Validation:** Validate wallet addresses, transaction amounts, and user inputs on the server.
* **Transaction Verification:** Check transaction errors, receipt status, and confirmations rather than relying only on successful submission.
* **Database Protection:** Do not commit databases containing real user information, passwords, or private keys. Add sensitive local files to `.gitignore`.
* **Network Safety:** Use test ETH on a local development blockchain. Do not use this application with real funds or mainnet private keys.

For production use, the application would require stronger authentication, secure key management, transaction monitoring, comprehensive testing, and independent security review.

## Future Enhancements

* [ ] Integrate MetaMask or another external wallet provider.
* [ ] Add transaction history with timestamps and transaction statuses.
* [ ] Improve authentication and password security.
* [ ] Add payment receipts and transaction confirmation tracking.
* [ ] Implement role-based access for users and merchants.
* [ ] Add automated tests for payment workflows and error handling.
* [ ] Improve the user interface and mobile responsiveness.
* [ ] Support configurable Ethereum test networks.

## License

Specify the license for this project by adding a `LICENSE` file to the repository. If you choose the MIT License, include the official MIT license text and update this section accordingly.

---

**Merchant Payment System — Exploring blockchain-powered payments with Python and Ethereum.**
