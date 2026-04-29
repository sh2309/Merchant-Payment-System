````markdown
# Merchant Payment System using Blockchain (Python & Ganache)

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-Web_Framework-black?logo=flask&logoColor=white)
![Web3.py](https://img.shields.io/badge/Web3.py-Ethereum-3C3C3D?logo=ethereum&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-Database-003B57?logo=sqlite&logoColor=white)
![Ganache](https://img.shields.io/badge/Ganache-Local_Blockchain-E4A663?logo=truffle&logoColor=white)

## About The Project

The Merchant Payment System is a blockchain-based web application that allows users and merchants to send, receive and manage Ethereum payments securely. Built using Python, Flask and Web3.py, the system uses a local Ethereum blockchain powered by Ganache to perform fast and transparent peer-to-peer transactions.

This project demonstrates how blockchain can be integrated into digital payment systems to provide secure, decentralized and real-time transactions without relying on traditional banking infrastructure.

## Key Features
- User Authentication: Secure Signup and Login system using username and password.
- Blockchain Wallet Integration: Users register with their Ethereum Public Address and Private Key from Ganache.
- Send Ethereum Payments: Users can send ETH to merchants or other users through signed blockchain transactions.
- Receive Ethereum Payments: Users can generate a QR code containing their Ethereum wallet address for easy payment collection.
- QR Code Generation: Simplifies receiving payments by allowing wallet addresses to be scanned instantly.
- Live Balance Tracking: Displays real-time ETH wallet balance fetched directly from the blockchain.
- Transaction Security: Transactions are signed using the sender’s private key before broadcasting.
- **Error Handling: Handles invalid wallet addresses, insufficient balance, and failed transactions.

## Technology Stack
- Backend: Python, Flask
- Blockchain Integration: Web3.py
- Blockchain Network: Ganache
- Database: SQLite3
- Frontend: HTML, CSS, Jinja2 Templates
- QR Code Generation: qrcode, OpenCV (cv2)

## Getting Started
### Prerequisites
Before running the project, make sure the following are installed:
1. Python 3.x
2. Ganache (Local Ethereum Blockchain)
3. Required Python libraries:
   - Flask
   - Web3
   - qrcode
   - opencv-python

### Installation & Setup
#### 1. Clone the Repository

```bash
git clone https://github.com/your-username/MerchantPaymentSystem_Using_Blockchain-Python-Ganache.git
cd MerchantPaymentSystem_Using_Blockchain-Python-Ganache
````

#### 2. Install Dependencies
```bash
pip install flask web3 qrcode opencv-python
```

#### 3. Start Ganache
* Open Ganache
* Start a **Quickstart Workspace**
* Ensure Ganache is running on:
```text
http://127.0.0.1:7545
```
Ganache will automatically generate test accounts with ETH for development.

#### 4. Initialize Database
Run the database setup script:
```bash
python init_db.py
```
This creates the required SQLite database and tables.

#### 5. Run the Application
```bash
python app.py
```
The Flask server will start at:
```text
http://localhost:5002
```

## Usage Workflow
### 1. Sign Up
Create a new account using:
* Username
* Password
* Ethereum Public Address (from Ganache)
* Private Key (from Ganache)

### 2. Log In
Log into the system using your registered credentials.

### 3. View Dashboard
After login, access the dashboard to:
* Check ETH balance
* Send ETH
* Receive ETH

### 4. Receive Payments
Generate a QR code linked to your Ethereum address and display it for payment.

### 5. Send Payments
Enter:
* Receiver Wallet Address
* ETH Amount
The application signs and broadcasts the transaction to Ganache.

### 6. Transaction Confirmation
Once successful, the transaction hash is displayed as proof of payment.

## Project Structure
```text
MerchantPaymentSystem_Using_Blockchain-Python-Ganache/
│
├── app.py              # Main Flask application
├── db_conns.py         # Database connection and queries
├── init_db.py          # Database initialization script
├── qr_gen.py           # QR code generation logic
├── user.db             # SQLite database
│
├── static/             # Static files (CSS, generated QR images)
│
└── templates/          # HTML templates for frontend pages
```

## Security Note
This project is intended for educational and development purposes only.
Private keys are stored locally in SQLite for testing convenience. In a production-grade system, private keys must never be stored in plaintext and should be secured using encryption or external wallet integrations.

## License
This project is licensed under the MIT License.
You are free to use, modify, and distribute this project for educational and development purposes.
