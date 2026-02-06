# Python Virtual Environment – Minimal Practical Demo

This repository is a **very small hands-on project** to understand what a **Python virtual environment (venv)** is and why it is used.

The project intentionally keeps things minimal so you can *see the effect of a virtual environment clearly*.

---

## 🎯 What this repo demonstrates

- How to create a Python virtual environment
- How package installation is **isolated per project**
- How the **same Python script** behaves differently:
  - with system Python
  - inside a virtual environment

---

## 📂 Project structure

venv-demo/
├── test.py # Simple Python script
└── README.md


> Note: The virtual environment folder (`myenv/`) is **not included** in the repo.
Each user creates it locally.

---

## 🧠 Prerequisites

Make sure Python is installed:

python3 --version


🚀 How to run this project

Follow these steps in order.

Step 1: Clone the repository
git clone <your-repository-url>
cd venv-demo

Step 2: Run the script WITHOUT a virtual environment
python3 test.py


Possible outcomes:

❌ ModuleNotFoundError: No module named 'requests'

✔ Script runs using system-installed packages

Both outcomes are expected.

Step 3: Create a virtual environment
python3 -m venv myenv


This creates a local virtual environment inside the myenv/ folder.

Step 4: Activate the virtual environment
macOS / Linux
source myenv/bin/activate

Windows (Git Bash)
source myenv/Scripts/activate


Your terminal prompt will change to:

(myenv)

Step 5: Install dependency inside the virtual environment
pip install requests


This installation is isolated to the virtual environment.

Step 6: Run the script again
python test.py


Expected output:

Requests version: <version_number>

Step 7: Deactivate the virtual environment
deactivate


Run again:

python3 test.py


You will notice the behavior differs from Step 6
