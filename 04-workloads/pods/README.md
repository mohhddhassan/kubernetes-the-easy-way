# Pods

A Pod is the smallest deployable unit in Kubernetes.  
It usually runs **one container**, but it can also run multiple tightly-coupled containers.

---

## Apply the Pod
```bash
kubectl apply -f nginx-pod.yaml
````

## Check Pod

```bash
kubectl get pods
```

## Describe Pod

```bash
kubectl describe pod nginx-pod
```

## Delete Pod

```bash
kubectl delete pod nginx-pod
```
