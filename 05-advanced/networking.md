# Networking Deep Dive

---

## CNI (Container Network Interface) Basics
CNI is basically a standard for how pods get their network interfaces & IP addresses.  
When a pod is created, CNI plugin comes into play → assigns IP address + connects the pod to the network.  

Popular CNIs: Flannel, Calico, Weave, Cilium.  
(Each has their own pros/cons like simplicity, security, performance).  

---

## How kube-proxy Works (iptables / IPVS)
kube-proxy is the component that handles service networking.  
Its main job → route traffic coming to a Service → forward to the correct Pod.  

It can do this in 2 modes:
- **iptables**: Uses Linux iptables rules. Common & default, works fine.  
- **IPVS**: Uses Linux IP Virtual Server, faster & scales better for large clusters.  

---

## Ingress vs LoadBalancer vs NodePort
- **NodePort**: Exposes your service on a static port of every node. Not flexible, mostly for dev/testing.  
- **LoadBalancer**: Gets an external load balancer from your cloud provider (AWS ELB, GCP LB, etc.). Works well in cloud.  
- **Ingress**: More advanced, acts like a reverse proxy + routing rules. Can handle multiple services behind a single IP/domain.  

👉 Best way in real world: Ingress with an Ingress Controller (like Nginx, Traefik).
