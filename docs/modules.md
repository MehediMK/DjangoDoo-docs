# 📦 DjangoDoo Modules Guide  

DjangoDoo is a **modular** framework built using Django, allowing you to create independent **feature modules** similar to Odoo. Each module has its own models, views, templates, and API endpoints while seamlessly integrating into the core system.  

---

## 🚀 What is a Module?  

A **module** in DjangoDoo is a self-contained application that extends the core functionality. It can be enabled or disabled dynamically without affecting the entire system.  

Each module can include:  
✔ **Models** – Define database tables  
✔ **Views** – Handle HTTP requests  
✔ **Templates** – Frontend HTML pages  
✔ **Static Files** – CSS, JS, images  
✔ **API Endpoints** – RESTful APIs (optional)  

---

## 📂 Module Directory Structure  

Each module is stored inside the `modules/` directory:  

```
djangodoo/
│── djangodoo/                 # Core framework functionality
│   ├── ...                    # All DjangoDoo files exists here.
│── ├── settings.py            # Django settings file
│── modules/                   # All independent feature modules
│   ├── sales/                 # Example module (Sales Management)
│   │   ├── models.py          # Database models
│   │   ├── views.py           # Business logic & controllers
│   │   ├── urls.py            # URL routing
│   │   ├── templates/sales/   # Frontend templates
│   │   ├── static/sales/      # Static assets (CSS, JS, images)
│   │   ├── api.py             # REST API endpoints (optional)
│   │   ├── __init__.py        # Module initialization
│   │   ├── admin.py           # Django Admin integration
│   │   ├── forms.py           # Django Forms (if needed)
│   │   ├── tests.py           # Unit tests for the module
│── manage.py                  # Django management script
```

---

## 🔨 How to Create a New Module  

### **Step 1: Create a Module Directory**  

Navigate to the `modules/` directory and create a new module:  

```bash
cd modules/
mkdir inventory
cd inventory
touch __init__.py models.py views.py urls.py api.py admin.py forms.py tests.py
mkdir templates/inventory static/inventory
```

---

### **Step 2: Define Models (`models.py`)**  

Create your database models inside `models.py`:  

```python
from django.db import models

class Product(models.Model):
    name = models.CharField(max_length=255)
    price = models.DecimalField(max_digits=10, decimal_places=2)
    stock = models.IntegerField()
    
    def __str__(self):
        return self.name
```

Run migrations to apply database changes:  

```bash
python manage.py makemigrations inventory
python manage.py migrate
```

---

### **Step 3: Create Views (`views.py`)**  

Define business logic and render templates:  

```python
from django.shortcuts import render
from .models import Product

def product_list(request):
    products = Product.objects.all()
    return render(request, "inventory/product_list.html", {"products": products})
```

---

### **Step 4: Define URL Routing (`urls.py`)**  

Connect your views to Django’s URL system:  

```python
from django.urls import path
from .views import product_list

urlpatterns = [
    path('products/', product_list, name="product_list"),
]
```

Include this module in the project's main `urls.py`:  

```python
from django.urls import include, path

urlpatterns = [
    path('inventory/', include('modules.inventory.urls')),
]
```

---

### **Step 5: Create Templates (`templates/inventory/product_list.html`)**  

Define an HTML template for the module:  

```html
{% extends 'base.html' %}
{% block content %}
    <h1>Product List</h1>
    <ul>
        {% for product in products %}
            <li>{{ product.name }} - ${{ product.price }}</li>
        {% endfor %}
    </ul>
{% endblock %}
```

---

### **Step 6: Register the Module in Django Admin (`admin.py`)**  

```python
from django.contrib import admin
from .models import Product

admin.site.register(Product)
```

Now, run the Django development server:  

```bash
python manage.py runserver
```

Visit **`http://127.0.0.1:8000/inventory/products/`** to see the module in action.

---

## 🛠 Dynamic Module Loading  

DjangoDoo supports **dynamic module activation/deactivation**. To register a new module, add it to `INSTALLED_APPS` dynamically in `settings.py`:

```python
import os

INSTALLED_APPS += [
    app for app in os.listdir("modules") if os.path.isdir(os.path.join("modules", app))
]
```

This ensures that any new module added to `modules/` is **automatically loaded**.

---

For more details, check our **GitHub Repository**. 🚀  

🔗 **GitHub:** [DjangoDoo Repository](https://github.com/MehediMK/djangodoo)  
🔗 **Join Discord:** [DjangoDoo Community](#)  
---