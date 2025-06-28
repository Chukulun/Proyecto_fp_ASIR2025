# Proyecto_fp_ASIR2025
Proyecto de Fin de Grado FP ASIR

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
Un recurso excelente que recomiendo para quienes quieran comenzar con Kubernetes.

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

## 🧱 Arquitectura

```plaintext
Usuario
  │
  ▼
Frontend (NodePort Service)
  │
  ▼
Backend (ClusterIP Service)
  │
  ▼
Pod (Go API REST)

