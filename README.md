# My DevOps Practice Project 🚀

## 📌 Project Description

This is a simple Node.js application deployed on an Ubuntu server (AWS EC2).
The purpose of this project is to practice DevOps concepts such as deployment, process management, and basic CI/CD automation.

---

## ⚙️ Technologies Used

* Node.js
* Git & GitHub
* Ubuntu (EC2 Server)
* PM2 (Process Manager)
* Cron Jobs (Automation)

---

## 🚀 Steps Performed

### 1. Application Setup

* Created `app.js` and `package.json`

### 2. Installed Node.js

```bash
sudo apt install nodejs
```

### 3. Ran Application

```bash
node app.js
```

---

## ❌ Errors Faced & Solutions

### 🔴 Error 1: Node not found

**Error:**

```
node: command not found
```

**Cause:**
Node.js was not installed

**Solution:**

```bash
sudo apt install nodejs
```

---

### 🔴 Error 2: Application not accessible via localhost

**Cause:**
Application was running on EC2 server, not on local machine

**Solution:**
Used public IP:

```
http://<ec2-public-ip>:3000
```

---

### 🔴 Error 3: Application not accessible via public IP

**Cause:**
Port 3000 was blocked in AWS Security Group

**Solution:**
Added inbound rule:

* Port: 3000
* Source: 0.0.0.0/0

---

### 🔴 Error 4: npm not found

**Cause:**
npm was not installed

**Solution:**

```bash
sudo apt install npm
```

---

### 🔴 Error 5: pm2 not found

**Cause:**
PM2 not installed

**Solution:**

```bash
sudo npm install -g pm2
```

---

## 🔄 Process Management (PM2)

```bash
pm2 start app.js
pm2 save
pm2 startup
```

**Purpose:**

* Keeps application running in background
* Automatically restarts on server reboot

---

## 🔁 Automation (Basic CI/CD)

Configured cron job:

```bash
crontab -e
```

Added:

```bash
* * * * * cd /home/ubuntu/my-app && git pull origin main && pm2 restart app
```

**Functionality:**

* Pulls latest code every minute
* Restarts application automatically

---

## 🎯 Final Outcome

* Application deployed on server
* Accessible via public IP
* Automatic updates from GitHub
* Application always running

---

## 🧠 Key Learnings

* Application deployment on Linux server
* Troubleshooting real-world errors
* Basic CI/CD pipeline setup
* Process management using PM2

---

## 👤 Author

Rohit – DevOps Practice
