# Kubernetes Basic Commands

## Cluster Info
- `kubectl version` → Show client and server versions.
- `kubectl cluster-info` → Display cluster information.
- `kubectl get nodes -o wide` → Show all nodes with details.

## Working with Pods
- `kubectl run mypod --image=nginx --restart=Never` → Run a single pod.
- `kubectl get pods -o wide` → Pod list with IPs and nodes.
- `kubectl describe pod mypod` → Pod details.

## Deployments
- `kubectl create deployment myapp --image=nginx` → Create deployment.
- `kubectl get deployments` → List deployments.
- `kubectl delete deployment myapp` → Delete deployment.
- `kubectl edit deployment myapp` → Edit deployment.


## Services
- `kubectl expose deployment myapp --type=NodePort --port=80` → Expose deployment.
- `kubectl get svc` → List services.

## Logs & Exec
- `kubectl logs mypod` → View pod logs.
- `kubectl exec -it mypod -- bash` → Enter pod container.

## Apply from YAML
- `kubectl apply -f simple-pod.yaml` → Create pod from file.
- `kubectl delete -f simple-pod.yaml` → Delete the same pod.
