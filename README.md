 # DVWA Kubernetes Deployment and Attack Demonstration

## 📌 Project Overview
This project sets up and deploys the **Damn Vulnerable Web Application (DVWA)** on a **local Kubernetes cluster (Minikube)**. The purpose is to showcase **three common web vulnerabilities** by executing real-world attacks. The vulnerabilities demonstrated are:

1. **SQL Injection**
2. **Cross-Site Scripting (XSS)**
3. **Command Injection**

## 🚀 Prerequisites
To run this project successfully, ensure you have the following installed:

- **Docker Desktop** (with Kubernetes enabled) or **Minikube**
- **Kubectl** (Kubernetes command-line tool)
- **Git**
- **A Web Browser** (to access the DVWA instance)

## 📂 Folder Structure
```
├── manifests/              # Kubernetes YAML configuration files
│   ├── dvwa-deployment.yaml  # Deployment definition for DVWA
│   ├── dvwa-service.yaml     # Service definition (NodePort)
│   ├── dvwa-ingress.yaml     # Ingress definition (optional)
│
├── screenshots/            # Screenshots of attacks performed
│   ├── sql-injection.png
│   ├── xss-attack.png
│   ├── command-injection.png
│
├── README.md               # Project documentation (this file)
├── .gitignore              # Files to be ignored in Git
```

## 🛠️ Deployment Steps
### 1️⃣ Clone the Repository
```sh
git clone https://github.com/your-username/dvwa-k8s-demo.git
cd dvwa-k8s-demo
```

### 2️⃣ Start Minikube
```sh
minikube start --driver=docker
```

### 3️⃣ Apply Kubernetes Manifests
```sh
kubectl apply -f manifests/
```

### 4️⃣ Verify Deployment
```sh
kubectl get pods
kubectl get services
```

### 5️⃣ Access DVWA
Run the following command to get the Minikube service URL:
```sh
minikube service dvwa --url
```
Open the displayed URL in your browser to access the **DVWA login page**.

---

## 🔥 Attack Demonstrations

### 1️⃣ SQL Injection
**Steps to exploit:**
1. Navigate to **Login Page**.
2. Enter the following credentials:
   - **Username:** `admin' --`
   - **Password:** `anything`
3. Click **Login** and you will be granted access without needing a valid password.
4. Screenshot: `screenshots/sql-injection.png`

### 2️⃣ Cross-Site Scripting (XSS)
**Steps to exploit:**
1. Navigate to the **'Vulnerable Input'** field in DVWA.
2. Enter the following script:
   ```html
   <script>alert("Hacked!");</script>
   ```
3. Click **Submit** and an alert box should appear.
4. Screenshot: `screenshots/xss-attack.png`

### 3️⃣ Command Injection
**Steps to exploit:**
1. Go to **'Ping a Host'** functionality.
2. Enter the following command:
   ```sh
   127.0.0.1; ls -la
   ```
3. Click **Submit** and observe the directory listing appearing in the response.
4. Screenshot: `screenshots/command-injection.png`

---

## 📤 Submission and Documentation
To document and submit this project:
1. **Take screenshots** of your Minikube setup, attack executions, and results.
2. **Push the project to GitHub:**
   ```sh
   git add .
   git commit -m "Added DVWA setup and attack screenshots"
   git push origin main
   ```
3. **Share the GitHub repo link** for submission.

---

## 📌 Conclusion
This project successfully deploys **DVWA on Kubernetes (Minikube)** and demonstrates **three common attack surfaces**. The goal is to understand **web security flaws** and how attackers exploit them in real-world scenarios.

For any questions or improvements, feel free to **contribute** or **raise an issue** in the repository!

**🔗 GitHub Repo:** [Your Repo Link Here]


