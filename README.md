# 🐍 Python Virtual Environment – Minimal Practical Demo

A **hands-on mini-project** to understand what a Python virtual environment (venv) is and why it matters.

This project is intentionally minimal so you can clearly see how virtual environments work in practice.

---

## 🎯 What You'll Learn

- ✅ How to create a Python virtual environment
- ✅ Why package installation should be **isolated per project**
- ✅ How the **same script** behaves differently with and without a venv

---

## 📂 Project Structure

```
venv-demo/
├── test.py          # Simple demo script
└── README.md        # This file
```

> **Note:** The virtual environment folder (`myenv/`) is **not** included in this repo.  
> You'll create it locally when following the steps below.

---

## 🧠 Prerequisites

Make sure Python 3 is installed on your system:

```bash
python3 --version
```

---

## 🚀 Step-by-Step Guide

### **Step 1: Clone the Repository**

```bash
git clone <your-repository-url>
cd venv-demo
```

---

### **Step 2: Run Without a Virtual Environment**

First, let's see what happens when we run the script using your system Python:

```bash
python3 test.py
```

**Possible outcomes:**

- ❌ `ModuleNotFoundError: No module named 'requests'`  
- ✅ Script runs (if `requests` is already installed globally)

Both are expected! This shows your script depends on system-wide packages.

---

### **Step 3: Create a Virtual Environment**

Now let's create an isolated environment for this project:

```bash
python3 -m venv myenv
```

This creates a `myenv/` folder containing a fresh Python environment.

---

### **Step 4: Activate the Virtual Environment**

**macOS / Linux:**
```bash
source myenv/bin/activate
```

**Windows (Command Prompt):**
```cmd
myenv\Scripts\activate
```

**Windows (Git Bash):**
```bash
source myenv/Scripts/activate
```

Once activated, your terminal prompt will change to:
```
(myenv) $
```

---

### **Step 5: Install Dependencies**

Install the required package **inside** the virtual environment:

```bash
pip install requests
```

This installation is **isolated** to this project only.

---

### **Step 6: Run the Script Again**

```bash
python test.py
```

**Expected output:**
```
Requests version: 2.31.0
```

✅ Success! The script now runs with the package installed in the virtual environment.

---

### **Step 7: Deactivate and Compare**

Exit the virtual environment:

```bash
deactivate
```

Your prompt returns to normal. Now run the script again:

```bash
python3 test.py
```

**Notice the difference:**  
The script may fail again (if `requests` isn't installed globally) or use a different version. This demonstrates **isolation**!

---

## 🧪 The `test.py` Script

Here's what the demo script does:

```python
import requests

print(f"Requests version: {requests.__version__}")
```

Simple, right? It just checks if the `requests` library is available and prints its version.

---

## 💡 Key Takeaways

| Without venv | With venv |
|--------------|-----------|
| Uses system-wide packages | Uses project-specific packages |
| Risk of version conflicts | Complete isolation |
| Changes affect all projects | Changes only affect this project |

**Why use virtual environments?**

- 🔒 **Isolation**: Each project has its own dependencies
- 🛡️ **Avoid conflicts**: Different projects can use different versions
- 📦 **Reproducibility**: Easy to share exact requirements with others
- 🧹 **Clean system**: Don't pollute your global Python installation

---

## 📚 Next Steps

- Create a `requirements.txt` file with `pip freeze > requirements.txt`
- Share your environment with: `pip install -r requirements.txt`
- Explore other virtual environment tools like `virtualenv`, `pipenv`, or `poetry`

---

## 🤝 Contributing

Found this helpful? Feel free to star ⭐ the repo or suggest improvements!

---

## 📝 License

This project is open source and available under the MIT License.

---

**Happy coding! 🚀**
