# 🐳 Custom Docker Images by Raja

This repo contains 5 production-safe Docker images you can use for DevOps labs, ACR, AKS, pipelines, monitoring, and more.

## 📦 Image List

| Image Name   | Description                     | Port | Folder         |
|--------------|----------------------------------|------|----------------|
| pythonapp    | Flask app                       | 5000 | `pythonapp/`   |
| nodeapp      | Node.js Express app             | 3000 | `nodeapp/`     |
| htmlapp      | Static HTML with NGINX          | 80   | `htmlapp/`     |
| nginxproxy   | Basic NGINX reverse proxy       | 80   | `nginxproxy/`  |
| healthcheck  | Flask app with `/health` route  | 5001 | `healthcheck/` |

## 🧪 How to Build and Push to ACR

```bash
ACR_NAME=myacrramraja
LOGIN_SERVER=$(az acr show --name $ACR_NAME --query loginServer --output tsv)

cd pythonapp
docker build -t pythonapp:1 .
docker tag pythonapp:1 $LOGIN_SERVER/pythonapp:1
docker push $LOGIN_SERVER/pythonapp:1
```

Repeat for other folders.

## 🧑‍💻 Created By

**Raja (K Ram Prasad)** – DevOps Engineer in Progress ❤️
