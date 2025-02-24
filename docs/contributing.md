# 🛠 Contributing to DjangoDoo  

Welcome to the **DjangoDoo** project! 🚀  
We appreciate your interest in contributing to this open-source **modular Django framework**, inspired by Odoo. Whether you're fixing a bug, adding a feature, or improving documentation, your contribution is valuable.  

---

## 📌 How to Contribute  

### 1️⃣ Fork the Repository  
1. Go to the [DjangoDoo GitHub Repository](https://github.com/MehediMK/djangodoo).
2. Click the **Fork** button (top right).
3. Clone your forked repository locally:  

```bash
git clone https://github.com/YOUR-USERNAME/djangodoo.git
cd djangodoo
```

4. Add the upstream repository:  

```bash
git remote add upstream https://github.com/MehediMK/djangodoo.git
```

---

### 2️⃣ Set Up the Development Environment  

1. **Create a virtual environment**:  

```bash
python -m venv env
source env/bin/activate  # For Linux/macOS
env\Scripts\activate      # For Windows
```

2. **Install dependencies**:  

```bash
pip install -r requirements.txt
```

3. **Apply migrations**:  

```bash
python manage.py migrate
```

4. **Run the development server**:  

```bash
python manage.py runserver
```

---

### 3️⃣ Pick an Issue & Work on It  

🔹 Check **[GitHub Issues](https://github.com/MehediMK/djangodoo/issues)** for open tasks.  
🔹 Comment on an issue before starting to avoid duplication.  
🔹 Create a new branch for your contribution:  

```bash
git checkout -b feature-branch-name
```

🔹 After making changes, test your code and commit:  

```bash
git add .
git commit -m "✨ Added new feature: [Feature Name]"
git push origin feature-branch-name
```

---

### 4️⃣ Submit a Pull Request (PR)  

Once your changes are ready:  
1. Go to **GitHub** and open a **Pull Request (PR)**.  
2. Provide a clear **title & description** of your changes.  
3. **Wait for a review** from maintainers.  

---

## 📋 Code Guidelines  

✔ Follow **PEP8** coding standards.  
✔ Use **descriptive commit messages** (e.g., `"🐛 Fixed bug in module loader"`).  
✔ Write **unit tests** for new features (`tests/` directory).  
✔ Use **black** for code formatting:  

```bash
black .
```

✔ Run pre-commit checks before pushing:  

```bash
pre-commit run --all-files
```

---

## 📢 How to Report Issues  

If you find a bug or have a feature request:  
🔹 Go to **[GitHub Issues](https://github.com/MehediMK/djangodoo/issues)**.  
🔹 Click **"New Issue"** and choose **Bug Report** or **Feature Request**.  
🔹 Provide clear details with screenshots (if applicable).  

---

## 💡 Ways to Contribute  

🚀 **Code Contributions** – Fix bugs, build new features  
📖 **Documentation** – Improve project documentation  
🐛 **Bug Reports** – Report and debug issues  
🌟 **Spread the Word** – Share DjangoDoo on LinkedIn, Twitter, or blogs  

---

## 🤝 Community & Support  

🔹 **GitHub Discussions** – Ask questions & share ideas  
🔹 **Discord Community** – Join our dev team (link coming soon)  
🔹 **Twitter/LinkedIn** – Tag us when sharing updates  

---

## ❤️ Thank You!  

Your contributions make DjangoDoo better every day! 🌟  
Happy Coding! 🚀  
---