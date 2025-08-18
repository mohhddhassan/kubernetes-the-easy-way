# ReplicaSets

A ReplicaSet makes sure that a specified number of identical Pods are always running.

---

## Apply the ReplicaSet
```bash
kubectl apply -f replicaset.yaml
````

## Check Pods

```bash
kubectl get pods
```

You should see **3 Pods** running.

---

## Scale the ReplicaSet

```bash
kubectl scale replicaset nginx-replicaset --replicas=5
```

---

## Delete ReplicaSet

```bash
kubectl delete replicaset nginx-replicaset
```