# Kubernetes Cheatsheet (Beginner Friendly)

## Pod Management
- `kubectl get pods` → List all pods in the current namespace.
- `kubectl describe pod <pod-name>` → Show details of a pod.
- `kubectl delete pod <pod-name>` → Delete a pod.
- `kubectl logs <pod-name>` → Show logs of a pod.
- `kubectl exec -it <pod-name> -- /bin/sh` → Get shell access inside pod.

## Deployment Management
- `kubectl get deployments` → List all deployments.
- `kubectl create deployment <name> --image=<image>` → Create a new deployment.
- `kubectl scale deployment <name> --replicas=3` → Scale pods up/down.
- `kubectl rollout restart deployment <name>` → Restart deployment.

## Services & Networking
- `kubectl get services` → List all services.
- `kubectl expose deployment <name> --type=NodePort --port=80` → Expose deployment externally.
- `kubectl describe service <service-name>` → Get details about service.

## Config & Secrets
- `kubectl get configmaps` → List all ConfigMaps.
- `kubectl get secrets` → List all secrets.
- `kubectl describe configmap <name>` → Inspect ConfigMap.

## Misc
- `kubectl get nodes` → List all nodes.
- `kubectl get namespaces` → List namespaces.
- `kubectl apply -f <file.yaml>` → Create/update resources from file.
- `kubectl delete -f <file.yaml>` → Delete resources from file.
