# Basic kubectl Commands

Once your cluster is ready, use `kubectl` to interact with it.

---

## Check Cluster Info
```bash
kubectl cluster-info
````

## Get Nodes

```bash
kubectl get nodes
```

## Get Pods

```bash
kubectl get pods -A
```

## Describe a Node/Pod

```bash
kubectl describe node <node-name>
kubectl describe pod <pod-name>
```

## Run a Test Pod

```bash
kubectl run nginx --image=nginx --port=80
kubectl get pods
```

## Delete a Pod

```bash
kubectl delete pod nginx
```

---

These are the most common commands you’ll use daily in Kubernetes.

