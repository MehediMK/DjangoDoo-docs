# 🚀 Getting Started with DjangoDoo  

Welcome to **DjangoDoo**, an open-source **modular** application framework built using Django, inspired by Odoo 17. This guide will help you set up DjangoDoo on your local machine and get started with development.  

---

## 🔥 Prerequisites  

Before you start, ensure you have the following installed on your system:  

✅ **Python 3.10+** - [Download Python](https://www.python.org/downloads/)  
✅ **Git** - [Download Git](https://git-scm.com/downloads)  
✅ **PostgreSQL (Recommended)** - [Download PostgreSQL](https://www.postgresql.org/download/)  
✅ **Virtual Environment (venv)** - Built into Python  
✅ **Django & Dependencies** - Installed via `pip`  

---

## 📥 Step 1: Clone the Repository  

First, clone the **DjangoDoo** repository from GitHub:  

```bash
git clone https://github.com/MehediMK/djangodoo.git
cd djangodoo
```

---

## 🏗 Step 2: Set Up a Virtual Environment  

Create a virtual environment to manage dependencies:  

```bash
python -m venv venv
```

Activate the virtual environment:  

```bash
# On macOS/Linux
source venv/bin/activate

# On Windows
venv\Scripts\activate
```

---

## 📦 Step 3: Install Dependencies  

Install all required packages using `pip`:  

```bash
pip install -r requirements.txt
```

Ensure that Django is installed:  

```bash
python -m django --version
```

---

## 🛠 Step 4: Configure the Database  

By default, DjangoDoo uses **SQLite**, but for production, PostgreSQL is recommended.  

### **Using SQLite (Default)**  
No additional configuration is required.  

### **Using PostgreSQL**  
1. Create a PostgreSQL database:  
   ```sql
   CREATE DATABASE djangodoo;
   ```
2. Update **`settings.py`** to configure PostgreSQL:  

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'djangodoo',
        'USER': 'your_username',
        'PASSWORD': 'your_password',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}
```

---

## 🔄 Step 5: Run Migrations  

Apply database migrations:  

```bash
python manage.py migrate
```

If using PostgreSQL, ensure you have created the database before running this command.

---

## 🚀 Step 6: Start the Development Server  

Run the Django server:  

```bash
python manage.py runserver
```

By default, the server starts at **`http://127.0.0.1:8000/`**. Open it in your browser to verify the setup.  

---

## 🔑 Step 7: Create a Superuser  

To access the **Django Admin Panel**, create a superuser:  

```bash
python manage.py createsuperuser
```

Follow the prompts to set up an admin username and password.  

Once done, visit **`http://127.0.0.1:8000/admin/`** and log in.

---

## 🎯 Step 8: Understanding the Project Structure  

DjangoDoo follows a **modular** structure where each feature is an independent module.  

```
djangodoo/
│── djangodoo/             # Core framework functionality
│   ├── ...                # All DjangoDoo files exists here.
│── modules/               # All independent feature modules
│   ├── sales/             # Example module (Sales Management)
│   ├── inventory/         # Example module (Inventory Management)
│── templates/             # Shared templates for frontend
│── static/                # Static files (CSS, JS, Images)
│── api/                   # API endpoints for REST support
│── settings.py            # Django settings file
│── manage.py              # Django management script
```

Each module inside `modules/` is **self-contained**, with its own models, views, templates, and API endpoints.

---

## 🛠 Step 9: Running Tests  

To ensure everything is working properly, run the test suite:  

```bash
python manage.py test
```

---

## 🔧 Step 10: Running Celery for Asynchronous Tasks (Optional)  

If the project requires asynchronous task processing with **Celery**, start the Celery worker:  

```bash
celery -A djangodoo worker --loglevel=info
```

---

## 🌟 Next Steps  

Now that DjangoDoo is set up, explore its features:  

📌 [Creating a New Module](modules.md)

---

## ❓ Need Help?  

For support, check our **GitHub Discussions** or join the **DjangoDoo Community**.  

🔗 **GitHub:** [DjangoDoo Repository](https://github.com/MehediMK/djangodoo)  
🔗 **Join Discord:** [DjangoDoo Community](#)  

🚀 Happy Coding with **DjangoDoo**! 🚀  
---