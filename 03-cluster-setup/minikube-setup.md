# Minikube Setup

Minikube is a tool that lets you run Kubernetes locally on your laptop.

---

## Step 1: Install Minikube
Follow official docs based on your OS:  
👉 [Minikube Installation Guide](https://minikube.sigs.k8s.io/docs/start/)

On Linux (example):
```bash
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
````

---

## Step 2: Start Minikube

```bash
minikube start
```

You’ll see it pull images and configure the cluster. After a few minutes, your cluster will be ready.

---

## Step 3: Verify

```bash
kubectl get nodes
```

Output:

```
NAME       STATUS   ROLES           AGE   VERSION
minikube   Ready    control-plane   1m    v1.30.0
```

---

## Step 4: Stop & Delete (Optional)

* Stop cluster:

  ```bash
  minikube stop
  ```
* Delete cluster:

  ```bash
  minikube delete
  ```
