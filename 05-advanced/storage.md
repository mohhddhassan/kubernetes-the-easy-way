# Storage in Kubernetes

---

## Persistent Volumes (PV)
PV is basically a piece of storage in the cluster that an admin provisions.  
It could be backed by local disk, NFS, cloud storage (EBS, GCE Persistent Disk, Azure Disk, etc.).  
Think of PV as the “physical storage resource”.

---

## Persistent Volume Claims (PVC)
PVC is how developers/pods request storage.  
Pod doesn’t care about the underlying storage type → it just says “I need 5Gi of storage” → PVC binds to a matching PV.  

So PV = supply, PVC = demand.  

---

## StorageClasses & Dynamic Provisioning
StorageClass defines the “type” of storage (fast SSD, cheap HDD, cloud managed disk etc).  
With StorageClasses, you don’t need to manually create PVs → K8s will **dynamically provision** a PV when a PVC requests it.  

Example: You create a PVC asking for `10Gi` using a `fast-ssd` StorageClass → K8s automatically provisions an EBS volume in AWS.  

---

👉 TLDR:
- PV = the actual storage.  
- PVC = request for storage.  
- StorageClass = template/rule for dynamic provisioning of PVs.  
