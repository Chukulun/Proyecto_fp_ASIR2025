# 🧱 Orquestación y desarrollo de aplicaciones en entornos contenerizados de alta disponibilidad

🚀 Proyecto final del ciclo **ASIR** en el IES Lucus Solis  
📅 Marzo 2025  
👤 Autor: Alejandro Beiroa Muñoz

---

## 🔧 Resumen del proyecto

Este trabajo nace con el objetivo de explorar y aplicar conocimientos de contenedores y orquestación mediante Kubernetes. Desarrollé una aplicación fullstack con backend en Golang y frontend en JavaScript, contenerizada con Docker y orquestada en un clúster Kubernetes (Minikube local + Azure AKS en la nube).

🧠 **Inspiración:**  
Este proyecto fue posible gracias al curso de Udemy:  
👉 [Kubernetes de Principiante a Experto](https://www.udemy.com/course/kubernetes-de-principiante-a-experto/?couponCode=ST16MT230625A)

---

## 🛠️ Tecnologías utilizadas

- Docker & Dockerfile  
- Kubernetes: Deployments, Services, ReplicaSets  
- Minikube (entorno local)  
- Azure AKS (entorno cloud)  
- Golang (API REST)  
- JavaScript + HTML (Frontend)  
- Nginx como servidor web  

---

## 📂 Estructura del repositorio

```
.
├── backend/
│   ├── main.go
│   ├── Dockerfile
│   └── backend.yaml
├── frontend/
│   ├── index.html
│   ├── Dockerfile
│   └── frontend.yaml
└── README.md
```

---

## 🚀 Instrucciones de despliegue

### 🔄 Despliegue local con Minikube

1. Inicia Minikube:

```bash
minikube start
```

2. Configura Docker para usar el entorno de Minikube:

```bash
eval $(minikube docker-env)
```

3. Construye las imágenes:

```bash
# Backend
docker build -t abeimun-backend ./backend

# Frontend
docker build -t abeimun-frontend ./frontend
```

4. Aplica los manifiestos:

```bash
kubectl apply -f backend/backend.yaml
kubectl apply -f frontend/frontend.yaml
```

5. Comprueba los pods y servicios:

```bash
kubectl get pods
kubectl get svc
```

6. Accede a la aplicación:

```bash
minikube service frontend-k8s-hands-on
```

---

### ☁️ Despliegue en Azure AKS

1. **Sube las imágenes a Docker Hub:**

```bash
docker tag abeimun-backend beiroa93/abeimun-backend:latest
docker tag abeimun-frontend beiroa93/abeimun-frontend:latest

docker push beiroa93/abeimun-backend
docker push beiroa93/abeimun-frontend
```

2. **Crea el clúster en Azure AKS desde el portal o CLI.**

3. **Conéctate al clúster:**

```bash
az aks get-credentials --resource-group <grupo-recursos> --name <nombre-cluster>
```

4. **Aplica los manifiestos:**

```bash
kubectl apply -f backend/backend.yaml
kubectl apply -f frontend/frontend.yaml
```

5. **Obtén la IP externa del servicio frontend:**

```bash
kubectl get svc
```

6. **Accede desde el navegador usando la IP y puerto proporcionados.**

---

## 📈 Lecciones aprendidas

- Multi-stage builds en Docker
- Servicios NodePort vs ClusterIP
- Escalabilidad horizontal con Kubernetes
- Configuración de CORS en APIs
- Integración local/nube (Minikube + Azure)

---

## 👨‍🎓 Créditos

Proyecto de fin de grado en ASIR 2024/2025  
Autor: Alejandro Beiroa Muñoz  
Centro: IES Lucus Solis, Sevilla

---

## 📝 Licencia

Uso educativo. Sientete libre de usarlo y compartirlo.
