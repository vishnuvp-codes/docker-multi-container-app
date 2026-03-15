

---

# Project Name

**Multi-Container Docker App (Flask + Nginx)**

---

# What This Project Does

This project shows how to run **two containers together using Docker Compose**.

The two containers are:

1. **Flask container** → runs a Python web application
2. **Nginx container** → receives requests from the browser and sends them to Flask

So the browser **does not talk directly to Flask**, it goes through **Nginx**.

---

# How It Works

```
Browser
   ↓
localhost:8080
   ↓
Nginx Container
   ↓
Flask Container
```

Steps:

1. User opens the browser
2. Browser sends request to **Nginx (port 8080)**
3. Nginx forwards the request to **Flask backend (port 5000)**
4. Flask returns the message

Output in browser:

```
Multi Container Docker App Working!
```

---

# Files in the Project

### backend/app.py

Flask application.

```python
@app.route("/")
def home():
    return "Multi Container Docker App Working!"
```

It shows a message when the website is opened.

---

### requirements.txt

Contains Python packages.

```
Flask
```

---

### Dockerfile

Used to create the **Flask container image**.

It:

1. Uses Python image
2. Installs Flask
3. Runs the Flask app

---

### nginx.conf

Configuration for **Nginx reverse proxy**.

It sends requests to the backend container.

```
proxy_pass http://backend:5000;
```

---

### docker-compose.yml

This file runs **multiple containers together**.

It starts:

• Flask backend container
• Nginx container

Command to run:

```
docker-compose up --build
```

---

# How to Run the Project

Step 1

```
docker-compose up --build
```

Step 2

Open browser:

```
http://localhost:8080
```

You will see:

```
Multi Container Docker App Working!
```

---

# What You Learned

This project teaches:

• Dockerfile
• Docker Compose
• Flask container
• Nginx reverse proxy
• Multi-container architecture

---

If you want, I can also show you **a slightly bigger DevOps project (Flask + Nginx + Database + Docker Compose)** which looks **much better in your portfolio.**
