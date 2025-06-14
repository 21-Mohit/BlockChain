# Blockchain Project

This project implements a basic blockchain system using Python and Flask. It includes functionality for creating blocks, adding transactions, mining new blocks, and maintaining consensus across multiple nodes in a decentralized network.

---

## Features

- **Blockchain**:
  - Create and manage blocks.
  - Add transactions to pending blocks.
  - Implement proof-of-work for mining blocks.
  - Maintain cryptographic integrity using SHA-256 hashing.

- **Flask API**:
  - `/mine`: Mine a new block and add it to the blockchain.
  - `/transactions/new`: Add a new transaction to the pending transactions list.
  - `/chain`: Retrieve the full blockchain.
  - `/nodes/register`: Register neighboring nodes in the network.
  - `/nodes/resolve`: Resolve conflicts and ensure consensus across nodes.

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/blockchain.git
   cd blockchain
   ```

2. Create a virtual environment:
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

3. Install dependencies:
   ```bash
   pip install Flask
   ```

---

## Usage

1. Start the Flask server:
   ```bash
   python server.py
   ```

2. Use the following endpoints to interact with the blockchain:
   - **Mine a block**:
     ```bash
     curl -X GET "http://localhost:5001/mine"
     ```
   - **Add a transaction**:
     ```bash
     curl -X POST -H "Content-Type: application/json" -d '{
       "sender": "sender-address",
       "recipient": "recipient-address",
       "amount": 5
     }' "http://localhost:5001/transactions/new"
     ```
   - **View the blockchain**:
     ```bash
     curl -X GET "http://localhost:5001/chain"
     ```
   - **Register nodes**:
     ```bash
     curl -X POST -H "Content-Type: application/json" -d '{
       "nodes": ["http://localhost:5002", "http://localhost:5003"]
     }' "http://localhost:5001/nodes/register"
     ```
   - **Resolve conflicts**:
     ```bash
     curl -X GET "http://localhost:5001/nodes/resolve"
     ```

---

## File Structure

- `blockchain.py`: Contains the `Blockchain` class with methods for managing blocks, transactions, and consensus.
- `server.py`: Implements the Flask API for interacting with the blockchain.
- `.gitignore`: Specifies files and directories to be ignored by Git.
- `ReadMe.md`: Documentation for the project.

---



