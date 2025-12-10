## Programmer Assessment Q4

This repository contains a broken web app built with Dash. Please follow the tasks below.

Tasks:
1. Clone this repo to your machine.
2. Fix missing dependencies and fill authors section in `pyproject.toml`.
3. Fix bugs prevent the app `main.py` from running.
4. Change port the app ruuning on to `10030`.
5. Commit you changes.
6. Update `README.md` with a instruction
   1. Assuming the user has a fresh minimum Linux installation with no python.
   2. Setup python and virtual environment for this app, remember to use the fixed `pyproject.toml`.
   3. How to run this app and how to access it without portforwarding.
7. Push all the changes to your own repository on Github, and provide a link to your own repo in your submission in the last.

---

## Setup Instructions

### Prerequisites
This guide assumes you have a fresh minimal Linux installation with no Python installed.

### Step 1: Install Python
```bash
# Update package list
sudo apt update

# Install Python 3 and pip
sudo apt install python3 python3-pip python3-venv -y

# Verify installation
python3 --version
```

### Step 2: Clone the Repository
```bash
# Clone this repository
git clone <your-repository-url>
cd Assessment-debugging
```

### Step 3: Create and Activate Virtual Environment
```bash
# Create a virtual environment
python3 -m venv venv

# Activate the virtual environment
source venv/bin/activate
```

### Step 4: Install Dependencies
```bash
# Install dependencies from pyproject.toml
pip install -e .

# Or install dependencies directly
pip install dash pandas numpy
```

### Step 5: Run the Application
```bash
# Run the Dash application
python3 main.py
```

The application will start and display:
```
Dash is running on http://127.0.0.1:10030/
```

### Step 6: Access the Application

#### Without Port Forwarding (Local Access):
If you're on the Linux machine directly:
- Open a web browser and navigate to: `http://127.0.0.1:10030/` or `http://localhost:10030/`

#### Without Port Forwarding (Remote Access):
If you're accessing the Linux machine remotely and want to access the app without port forwarding:

1. **Find your server's IP address:**
   ```bash
   hostname -I
   ```

2. **Modify the app to bind to all interfaces:**
   Edit `main.py` and change the last line to:
   ```python
   app.run(debug=True, port=10030, host='0.0.0.0')
   ```

3. **Ensure firewall allows the port:**
   ```bash
   sudo ufw allow 10030
   ```

4. **Access from any device on the same network:**
   Open a browser and navigate to: `http://<server-ip-address>:10030/`
   
   Example: `http://192.168.1.100:10030/`

### Deactivating the Virtual Environment
When you're done, you can deactivate the virtual environment:
```bash
deactivate
```
