# Config & Secrets Management

---

## ConfigMaps
ConfigMaps are basically used for storing non-sensitive configuration data.  
Think of it like key-value pairs (like environment variables).  
Example: If your app needs to know what environment it’s running in (`dev`, `prod`), you don’t want to hardcode that in the pod spec → use a ConfigMap.  

Ways you can use ConfigMaps:
- Pass values as ENV variables into your container.
- Mount it as a volume (file) inside the container.
- Directly read it via `kubectl`.

---

## Secrets
Secrets are also key-value pairs **but meant for sensitive info** (like passwords, API keys, tokens).  
The values are **base64 encoded** (not fully encrypted, so don’t think it’s very safe by itself).  

Example: DB password, SSH keys.  
You can mount them into your pod as env vars or files just like ConfigMaps.  

---

## Best Practices for Managing Sensitive Info
- Never hardcode passwords/tokens in YAML files.  
- Use Secrets for sensitive data, ConfigMaps for normal configs.  
- For production: Use external secret managers (like HashiCorp Vault, AWS Secrets Manager, Azure Key Vault) integrated with K8s instead of storing directly in the cluster.  
- Always enable encryption at rest for Kubernetes Secrets (supported by kube-apiserver).  
