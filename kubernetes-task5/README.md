# DevOps Internship – Task 5 (Kubernetes Concepts)

## 📌 Topics Covered
1. **Namespace** – Virtual clusters for resource isolation
2. **Service Types** – Difference between ClusterIP, NodePort, LoadBalancer
3. **ConfigMaps** – Storing and injecting non-confidential configuration
4. **Rolling Updates** – Updating deployments with zero downtime

## 🚀 Summary

### 1. Namespace
Namespaces allow organizing Kubernetes resources into virtual clusters.

### 2. Service Types
- **ClusterIP** – Internal cluster access only
- **NodePort** – Expose service on a port of each node
- **LoadBalancer** – Use cloud provider's LB for external traffic

### 3. ConfigMaps
ConfigMaps store non-secret config data in key-value pairs and inject them into pods.

### 4. Rolling Updates
Update deployments without downtime using `kubectl set image` and monitor with `kubectl rollout status`.

## 📤 Submission
After completing, submit your GitHub repository link at:
[Google Form Link](https://forms.gle/LyP4TSLqr7HpGQN36)
