# 🚀 DevOps Tools — Installation & Verification

<p align="center">
  <b>🔥 Complete DevOps Environment Setup for Windows 11 + WSL 2</b><br>
  <i>Install → Verify → Test → Ready for Hands-on DevOps 🚀</i>
</p>

<p align="center">

![Windows](https://img.shields.io/badge/OS-Windows%2011-0078D4?style=for-the-badge&logo=windows&logoColor=white)
![WSL](https://img.shields.io/badge/WSL-2-4D4D4D?style=for-the-badge&logo=linux&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Desktop-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-Minibuke-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)

</p>

<p align="center">

![Helm](https://img.shields.io/badge/Helm-Package%20Manager-0F1689?style=for-the-badge&logo=helm&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-Automation-EE0000?style=for-the-badge&logo=ansible&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-IaC-844FBA?style=for-the-badge&logo=terraform&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-LTS-339933?style=for-the-badge&logo=node.js&logoColor=white)

</p>

---

## 🎯 Project Objective

This repository provides a **clean, practical and production-oriented DevOps workstation setup** for Windows 11.

The environment includes:

| # | Tool | Purpose |
|---|------|---------|
| 1 | 🐧 WSL 2 | Linux environment on Windows |
| 2 | 🐳 Docker Desktop | Containerization |
| 3 | ☸️ Minikube | Local Kubernetes cluster |
| 4 | ☸️ kubectl | Kubernetes CLI |
| 5 | ⎈ Helm | Kubernetes package management |
| 6 | 🤖 Ansible | Configuration & automation |
| 7 | 🟢 Node.js | JavaScript runtime |
| 8 | 📦 npm | Node.js package manager |
| 9 | 🏗️ Terraform | Infrastructure as Code |
| 10 | 💻 VS Code | Development & DevOps workspace |

---

# 🛠️ Installation & Verification

> ⚠️ **Important:** Run Windows commands in **PowerShell as Administrator** unless stated otherwise.  
> Linux/WSL commands should be executed inside **Ubuntu/WSL**.

---

## 1️⃣ 🐧 WSL 2

### Install WSL

```powershell
wsl --install
```

### Set WSL 2 as default

```powershell
wsl --set-default-version 2
```

### Verify WSL

```powershell
wsl --status
```

> 🔄 If Windows asks for a restart, **restart Windows first**, then continue with the remaining commands.

---

## 2️⃣ 🐳 Docker Desktop

### Install Docker Desktop

```powershell
winget install --id Docker.DockerDesktop -e
```

### Verify Docker

```powershell
docker --version
```

### Verify Docker Compose

```powershell
docker compose version
```

### 🧪 Docker Test

```powershell
docker run hello-world
```

Expected result:

```text
Hello from Docker!
```

---

## 3️⃣ ☸️ Minikube

### Install Minikube

```powershell
winget install --id Kubernetes.minikube -e
```

### Verify Minikube

```powershell
minikube version
```

### Start Minikube with Docker driver

```powershell
minikube start --driver=docker
```

---

## 4️⃣ ☸️ kubectl

### Install kubectl

```powershell
winget install --id Kubernetes.kubectl -e
```

### Verify kubectl

```powershell
kubectl version --client
```

### Verify Kubernetes Node

```powershell
kubectl get nodes
```

### Verify Kubernetes Pods

```powershell
kubectl get pods -A
```

---

## 5️⃣ ⎈ Helm

### Install Helm

```powershell
winget install --id Helm.Helm -e
```

### Verify Helm

```powershell
helm version
```

---

## 6️⃣ 🤖 Ansible

Ansible is installed through **WSL / Ubuntu**.

### Update Ubuntu packages

```powershell
wsl -d Ubuntu -- sudo apt update
```

### Install Ansible

```powershell
wsl -d Ubuntu -- sudo apt install -y ansible
```

### Verify Ansible

```powershell
wsl -d Ubuntu -- ansible --version
```

### 🧪 Ansible Test

```powershell
wsl -d Ubuntu -- ansible localhost -m ping
```

Expected result should contain:

```text
SUCCESS
pong
```

---

## 7️⃣ 🟢 Node.js

> 💡 Run the following command inside **Ubuntu / WSL**, not normal Windows PowerShell.

### Install Node.js LTS

```bash
sudo apt update && sudo apt install -y curl && curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash - && sudo apt install -y nodejs
```

### Verify Node.js

```bash
node --version
```

---

## 8️⃣ 📦 npm

npm normally comes bundled with Node.js.

### Verify npm

```bash
npm --version
```

> ✅ If Node.js is installed correctly, npm should normally be available as well.

---

## 9️⃣ 🏗️ Terraform

### Install Terraform

```powershell
winget install --id Hashicorp.Terraform -e
```

### Verify Terraform

```powershell
terraform --version
```

### 🧪 Terraform Test

```powershell
terraform version
```

---

## 🔟 💻 Visual Studio Code

### Install VS Code

```powershell
winget install --id Microsoft.VisualStudioCode -e
```

### Verify VS Code

```powershell
code --version
```

---

# 🧪 Complete Environment Test

After installation, run these tests in order.

### Step 1 — Docker

```powershell
docker run hello-world
```

### Step 2 — Start Kubernetes

```powershell
minikube start --driver=docker
```

### Step 3 — Verify Kubernetes

```powershell
kubectl get nodes
kubectl get pods -A
```

### Step 4 — Verify Helm

```powershell
helm version
```

### Step 5 — Verify Terraform

```powershell
terraform version
```

### Step 6 — Verify Ansible

```powershell
wsl -d Ubuntu -- ansible localhost -m ping
```

---

# ✅ Final Verification Checklist

| Tool | Install | Verify | Test |
|------|:------:|:------:|:----:|
| 🐧 WSL 2 | ✅ | `wsl --status` | — |
| 🐳 Docker | ✅ | `docker --version` | `docker run hello-world` |
| 🐳 Docker Compose | — | `docker compose version` | — |
| ☸️ Minikube | ✅ | `minikube version` | `minikube start --driver=docker` |
| ☸️ kubectl | ✅ | `kubectl version --client` | `kubectl get nodes` |
| ⎈ Helm | ✅ | `helm version` | — |
| 🤖 Ansible | ✅ | `ansible --version` | `ansible localhost -m ping` |
| 🟢 Node.js | ✅ | `node --version` | — |
| 📦 npm | — | `npm --version` | — |
| 🏗️ Terraform | ✅ | `terraform --version` | `terraform version` |
| 💻 VS Code | ✅ | `code --version` | — |

---

# 🔄 DevOps Toolchain

```text
                 ┌─────────────────┐
                 │   👨‍💻 Developer   │
                 └────────┬────────┘
                          │
                          ▼
                    ┌───────────┐
                    │    Git    │
                    └─────┬─────┘
                          │
                          ▼
                    ┌───────────┐
                    │  Jenkins  │
                    └─────┬─────┘
                          │
             ┌────────────┴────────────┐
             ▼                         ▼
       ┌───────────┐             ┌────────────┐
       │  Ansible  │             │ Terraform  │
       └─────┬─────┘             └──────┬─────┘
             │                           │
             └────────────┬──────────────┘
                          ▼
                    ┌───────────┐
                    │  Docker   │
                    └─────┬─────┘
                          │
                          ▼
                    ┌───────────┐
                    │ Kubernetes│
                    └─────┬─────┘
                          │
                          ▼
                     ☁️ Cloud
```

---

# 📁 Suggested Repository Structure

```text
DevOps-Tools-Installation-Verification/
│
├── README.md
│
├── docker/
├── kubernetes/
├── helm/
├── ansible/
├── terraform/
├── jenkins/
│
└── docs/
```

---

# 🚨 Common Troubleshooting

### ❌ Docker command not recognized

```powershell
docker --version
```

If not recognized:

1. Confirm Docker Desktop is installed.
2. Start Docker Desktop.
3. Close and reopen PowerShell.
4. Check Docker Desktop integration/settings.

---

### ❌ Minikube cannot start

Check Docker:

```powershell
docker --version
```

Then:

```powershell
minikube status
```

Try:

```powershell
minikube start --driver=docker
```

---

### ❌ kubectl cannot connect to Kubernetes

Check:

```powershell
minikube status
```

Then:

```powershell
kubectl get nodes
```

If Minikube is stopped:

```powershell
minikube start --driver=docker
```

---

### ❌ Ansible command not found

Verify installation:

```powershell
wsl -d Ubuntu -- ansible --version
```

If required:

```powershell
wsl -d Ubuntu -- sudo apt update
wsl -d Ubuntu -- sudo apt install -y ansible
```

---

### ❌ Node.js / npm not found in WSL

Run inside Ubuntu:

```bash
node --version
npm --version
```

If Node.js is missing, reinstall Node.js LTS using the installation command above.

---

# 🏆 Ready for DevOps Practice?

Once all checks are successful, your workstation is ready for:

- 🐳 Docker containerization
- ☸️ Kubernetes deployments
- ⎈ Helm charts
- 🤖 Ansible automation
- 🏗️ Terraform IaC
- 🔄 CI/CD pipelines
- 🔐 DevOps security practices
- ☁️ Azure / AWS cloud labs
- 🚀 Production-style deployment practice

---

## ⭐ Recommended Learning Flow

```text
Linux
  ↓
Git & GitHub
  ↓
YAML
  ↓
Docker
  ↓
Docker Compose
  ↓
Jenkins / CI-CD
  ↓
Ansible
  ↓
Terraform
  ↓
Kubernetes
  ↓
Helm
  ↓
Azure / AWS
  ↓
🚀 Production DevOps
```

---

<p align="center">

### 🔥 Install. Verify. Break. Fix. Automate. Deploy. 🚀

<b>DevOps is not just about tools — it's about solving problems.</b>

</p>
