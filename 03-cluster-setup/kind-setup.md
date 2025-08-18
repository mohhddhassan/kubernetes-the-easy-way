# Kind Setup

Kind (Kubernetes IN Docker) is another easy way to run Kubernetes clusters for learning or testing.

---

## Step 1: Install Kind
👉 [Kind Installation Guide](https://kind.sigs.k8s.io/docs/user/quick-start/)

On Linux/macOS:
```bash
GO111MODULE="on" go install sigs.k8s.io/kind@v0.22.0
````

Or use pre-built binaries from GitHub releases.

---

## Step 2: Create a Cluster

```bash
kind create cluster --name demo
```

---

## Step 3: Verify

```bash
kubectl get nodes
```

Output:

```
NAME                 STATUS   ROLES           AGE   VERSION
kind-control-plane   Ready    control-plane   1m    v1.30.0
```

---

## Step 4: Delete Cluster

```bash
kind delete cluster --name demo
```

````