
# Despliegue de Grafana con Docker y Kubernetes

## 1. Descripción del proyecto

Este proyecto consiste en desplegar la plataforma Grafana
utilizando Kubernetes sobre Docker mediante Minikube.

Se implementan los conceptos de Pod, Deployment,
ReplicaSet y Service.

## 2. Objetivo

Implementar una aplicación mediante Kubernetes,
administrando sus réplicas y comprobando su
disponibilidad y exposición mediante un servicio.

## 3. Tecnologías utilizadas

- Docker Desktop
- Kubernetes
- Minikube
- kubectl
- Grafana
- YAML

## 4. Arquitectura

El Deployment administra dos réplicas de Grafana
mediante un ReplicaSet.

Cada réplica ejecuta un Pod con un contenedor
de Grafana.

El acceso a la plataforma se realiza mediante
un Service tipo NodePort.

## 5. Archivos de configuración

- kubernetes/deployment.yaml
- kubernetes/service.yaml

## 6. Despliegue

```bash
kubectl apply -f kubernetes/deployment.yaml
kubectl apply -f kubernetes/service.yaml
```

## 7. Verificación

```bash
kubectl get nodes
kubectl get deployments
kubectl get replicasets
kubectl get pods
kubectl get services
```

## 8. Escalamiento

Para aumentar a tres réplicas:

```bash
kubectl scale deployment grafana-deployment --replicas=3
```

Para regresar a dos:

```bash
kubectl scale deployment grafana-deployment --replicas=2
```

## 9. Recuperación automática

Se eliminó un Pod manualmente y se comprobó
que ReplicaSet creó automáticamente uno nuevo
para mantener las dos réplicas configuradas.

## 10. Exposición

Grafana se expone mediante un Service NodePort
utilizando el puerto 30080.

## 11. Usos de Grafana

- Monitoreo de infraestructura.
- Visualización de métricas.
- Supervisión de aplicaciones.
- Análisis de datos.
- Creación de dashboards.

## 12. Evidencias

Las capturas del despliegue se encuentran
en la carpeta evidencias.
