# Deployments

A Deployment provides declarative updates for Pods and ReplicaSets.  
It’s the most common way to run applications in Kubernetes.

---

## Apply the Deployment
```bash
kubectl apply -f deployment.yaml
````

## Check Pods

```bash
kubectl get pods
```

---

## Rolling Update

Update the image version inside `deployment.yaml` and re-apply:

```bash
kubectl apply -f deployment.yaml
```

Kubernetes will update Pods **one by one** (rolling update).

---

## Rollback

```bash
kubectl rollout undo deployment nginx-deployment
```

---

## Delete Deployment

```bash
kubectl delete deployment nginx-deployment
```