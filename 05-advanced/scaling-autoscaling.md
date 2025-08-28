---
# Scaling & Autoscaling in Kubernetes 📈

---

## Manual Scaling
Sometimes we just need more pods straight away – nothing fancy.  
That’s where manual scaling comes in.  

Example:
```sh
kubectl scale deployment nginx-deployment --replicas=5
````

Now k8s will make sure **5 pods of nginx** are always running.
But this is still manual – you gotta update it yourself when traffic changes.

---

## Horizontal Pod Autoscaler (HPA)

This is where k8s gets smart 🧠.
HPA automatically adds/removes pods based on **CPU/memory usage** (or even custom metrics if you configure it).

Example:

```sh
kubectl autoscale deployment nginx-deployment --cpu-percent=50 --min=1 --max=10
```

Here:

* If CPU usage of pods > 50%, new pods will spin up.
* If traffic cools down, pods will scale back to as low as 1.
* Super useful for apps with unpredictable traffic.

---

## Vertical Pod Autoscaler (VPA)

HPA scales **pods count**, but sometimes the pod itself needs more power 💪.
That’s where VPA comes in.

* It adjusts the **CPU/Memory requests & limits** of a pod.
* Example: Your pod always runs out of memory → VPA bumps up memory automatically.

👉 Downsides: Restart of pods is needed when resources change. So usually used for batch jobs or apps that can handle restarts.

---

## Cluster Autoscaler

Okay, now imagine you’ve got HPA asking for more pods,
but your cluster doesn’t have enough worker nodes to host them. 🚨

That’s where **Cluster Autoscaler** helps:

* On cloud (EKS/GKE/AKS), it can automatically add new nodes.
* When traffic drops, it can also remove unused nodes to save cost.

---

## TLDR:

* **Manual scaling** → You set replicas.
* **HPA** → Scales pods count automatically.
* **VPA** → Adjusts pod resources automatically.
* **Cluster Autoscaler** → Scales the worker nodes in the cluster.

Kubernetes = “auto mode ON” 😎

```

---
