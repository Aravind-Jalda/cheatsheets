# 🔹 1. Cluster Info & Context

```bash
kubectl cluster-info
kubectl get nodes
kubectl config get-contexts
kubectl config use-context <context>
```

👉 Used to verify cluster access and switch environments

---

# 🔹 2. Pods (Most Fundamental Unit)

### Create pod

```bash
kubectl run nginx --image=nginx
```

### List pods

```bash
kubectl get pods
kubectl get pods -o wide
```

### Describe pod

```bash
kubectl describe pod <pod-name>
```

### Delete pod

```bash
kubectl delete pod <pod-name>
```

---

# 🔹 3. Deployments (VERY IMPORTANT)

### Create deployment

```bash
kubectl create deployment myapp --image=nginx
```

### Scale deployment

```bash
kubectl scale deployment myapp --replicas=3
```

### Update image

```bash
kubectl set image deployment/myapp nginx=nginx:latest
```

### Rollout status

```bash
kubectl rollout status deployment/myapp
```

### Rollback

```bash
kubectl rollout undo deployment/myapp
```

👉 Interview tip:
Be ready to explain **why Deployment over Pod**

---

# 🔹 4. Services (Networking)

### Create service (expose deployment)

```bash
kubectl expose deployment myapp --type=NodePort --port=80
```

### List services

```bash
kubectl get svc
```

---

👉 Know types:

* ClusterIP (default)
* NodePort
* LoadBalancer

---

# 🔹 5. Namespaces

```bash
kubectl get ns
kubectl create ns dev
kubectl config set-context --current --namespace=dev
```

👉 Used for environment separation

---

# 🔹 6. Logs & Debugging (VERY IMPORTANT)

### Logs

```bash
kubectl logs <pod-name>
```

### Exec into pod

```bash
kubectl exec -it <pod-name> -- /bin/bash
```

### Describe resource

```bash
kubectl describe pod <pod-name>
```

---

👉 Interview gold:
If something fails → **logs + describe**

---

# 🔹 7. YAML (Declarative Approach)

### Apply config

```bash
kubectl apply -f deployment.yaml
```

### Delete config

```bash
kubectl delete -f deployment.yaml
```

---

👉 Interview tip:
Imperative vs Declarative (VERY COMMON QUESTION)

---

# 🔹 8. ConfigMaps & Secrets

### Create configmap

```bash
kubectl create configmap myconfig --from-literal=key=value
```

### Create secret

```bash
kubectl create secret generic mysecret --from-literal=password=1234
```

---

👉 Know difference:

* ConfigMap → non-sensitive
* Secret → sensitive data

---

# 🔹 9. Resource Monitoring

```bash
kubectl top pod
kubectl top node
```

👉 Requires metrics server

---

# 🔹 10. Labels & Selectors

```bash
kubectl label pod mypod env=dev
kubectl get pods -l env=dev
```

👉 Used heavily in:

* deployments
* services

---

# 🔹 11. Port Forwarding (Debugging)

```bash
kubectl port-forward pod/mypod 8080:80
```

👉 Access pod locally without service

---

# 🔹 12. Get Everything (Quick Debug)

```bash
kubectl get all
```

---

# 🔥 Most Important Commands (Focus These)

If interviewer pushes you, these matter most:

```bash
kubectl get pods
kubectl describe pod
kubectl logs
kubectl exec
kubectl apply -f
kubectl get svc
kubectl rollout
kubectl scale
```

---

# 🧠 Interview-Level Understanding (This is key)

### Instead of saying:

❌ “Deployment manages pods”

Say:
✅ “Deployment ensures desired state by managing ReplicaSets and automatically handles scaling, updates, and self-healing of pods”

---
