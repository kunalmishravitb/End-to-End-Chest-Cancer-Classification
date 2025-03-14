# 🫁 Chest Cancer Classification using MLflow & DVC 🚀

## 🔄 Workflows

1️⃣ Update `config.yaml`\
2️⃣ Update `secrets.yaml` *(Optional)*\
3️⃣ Update `params.yaml`\
4️⃣ Update the entity\
5️⃣ Update the configuration manager in `src config`\
6️⃣ Update the components\
7️⃣ Update the pipeline\
8️⃣ Update `main.py`\
9️⃣ Update `dvc.yaml`\
🔟 Update `app.py`

---

## 🛠️ How to Run?

### 📝 Steps:

#### 🔹 Clone the Repository

```bash
git clone https://github.com/kunalmishravitb/End-to-End-Chest-Cancer-Classification.git
```

#### 🔹 Step 1️⃣ - Create a Conda Environment

```bash
conda create -n chest python=3.10 -y
conda activate chest
```

#### 🔹 Step 2️⃣ - Install the Requirements

```bash
pip install -r requirements.txt
```

#### ▶️ Run the Application

```bash
python app.py
```

Then, open your browser and visit **localhost:8080**

---

## 📚 MLflow

📄 [MLflow Documentation](https://mlflow.org/docs/latest/index.html)
📺 [MLflow Tutorial](https://youtube.com/playlist?list=PLkz_y24mlSJZrqiZ4_cLUiP0CBN5wFmTb&si=zEp_C8zLHt1DzWKK)

📌 **Command to start MLflow UI**

```bash
mlflow ui
```

### 🌐 DagsHub Integration

🔗 [DagsHub](https://dagshub.com/)

```bash
export MLFLOW_TRACKING_URI=https://dagshub.com/kunalmishravitb/End-to-End-Chest-Cancer-Classification.mlflow
export MLFLOW_TRACKING_USERNAME=kunalmishravitb
export MLFLOW_TRACKING_PASSWORD=****************************************
```

---

## 📂 DVC Commands

🔹 **1️⃣ Initialize DVC**
```bash
dvc init
```

🔹 **2️⃣ Run the pipeline**
```bash
dvc repro
```

🔹 **3️⃣ Visualize the pipeline**
```bash
dvc dag
```

---

## 🏗️ About MLflow & DVC

### 🚀 **MLflow**
✅ Production-grade experiment tracking  
✅ Logs & tags models for easy reproducibility  
✅ Model registry & deployment support  

### ⚡ **DVC (Data Version Control)**
✅ Lightweight for proof-of-concept (PoC) projects  
✅ Experiment tracking with data management  
✅ Supports pipeline orchestration  

---

# 🌍 AWS CI/CD Deployment with GitHub Actions

## 🛡️ 1️⃣ Login to AWS Console

## 🔑 2️⃣ Create IAM User for Deployment

### ✅ Required Permissions:

🔹 **1️⃣ EC2 Access** – To manage virtual machines  
🔹 **2️⃣ ECR Access** – To store & retrieve Docker images  

### 🛠️ Deployment Steps:

🔹 **Build a Docker image** of the source code  
🔹 **Push the image** to ECR  
🔹 **Launch an EC2 instance**  
🔹 **Pull the image** from ECR in EC2  
🔹 **Run the container** in EC2  

📝 **IAM Policies to Attach:**

✔️ `AmazonEC2ContainerRegistryFullAccess`  
✔️ `AmazonEC2FullAccess`  

---

## 🏅 3️⃣ Create an ECR Repository

📂 Save the **ECR URI**: `*****.dkr.ecr.us-east-1.amazonaws.com/chest-cancer-classification`

---

## 💻 4️⃣ Create an EC2 Instance (Ubuntu)

## 🛠️ 5️⃣ Install Docker in EC2

```bash
# Optional
sudo apt-get update -y
sudo apt-get upgrade -y

# Required
curl -fsSL https://get-docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker ubuntu
newgrp docker
```

---

## 🔄 6️⃣ Configure EC2 as a Self-Hosted Runner

Navigate to **GitHub → Settings → Actions → Runners → New Self-Hosted Runner**, then follow the setup commands.

---

## 🔒 7️⃣ Set Up GitHub Secrets

```bash
AWS_ACCESS_KEY_ID=***************
AWS_SECRET_ACCESS_KEY=***************
AWS_REGION=us-east-1
AWS_ECR_LOGIN_URI=*****.dkr.ecr.us-east-1.amazonaws.com
ECR_REPOSITORY_NAME=chest-cancer-classification
```

---

