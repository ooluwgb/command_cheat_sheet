
# Kubernetes Commands

### Update Operation
To update the `defaultVolumeSize` for a project:
```bash
db.projects.update(
  { "name": "Project_Name" },
  { $set: { "defaultVolumeSize": NumberLong("New_Size_Value_in_Bytes") } }
)
```

### Apply Dataset Scripts
Apply the `script-job-index.yaml` and `script-job-mongo.yaml` scripts:
```bash
cat script-job-index.yaml | path/to/utility-scripts/process-manifests.py | kubectl apply -n namespace-name -f -
cat script-job-mongo.yaml | path/to/utility-scripts/process-manifests.py | kubectl apply -n namespace-name -f -
```

### Copy File from Pod
Copy a file from a Kubernetes pod to the local system:
```bash
kubectl cp -n namespace-name pod-name:/path/to/source/file ./destination-file.csv
```

### Retrieve Pod by Username
Search for pods by the starting username:
```bash
kubectl get po -n namespace-name -l dominodatalab.com/starting-user-username=username
```

### Check Pod Logs
Retrieve logs from a specific pod:
```bash
kubectl logs pod-name -n namespace-name
```

### Execute Command in a Running Pod
Run a command inside a running pod:
```bash
kubectl exec -it pod-name -n namespace-name -- command
```

### Describe a Pod
View detailed information about a pod:
```bash
kubectl describe pod pod-name -n namespace-name
```

### View All Pods in a Namespace
List all pods in a specific namespace:
```bash
kubectl get pods -n namespace-name
```

### Delete a Pod
Delete a specific pod:
```bash
kubectl delete pod pod-name -n namespace-name
```

### Apply Manifest File
Apply a Kubernetes manifest file:
```bash
kubectl apply -f manifest-file.yaml -n namespace-name
```

### Create Namespace
Create a new namespace:
```bash
kubectl create namespace namespace-name
```

### Get All Resources in a Namespace
List all resources in a namespace:
```bash
kubectl get all -n namespace-name
```

### Get Node Information
View all nodes in the cluster:
```bash
kubectl get nodes
```

### Debugging Node Issues
Describe a node to investigate issues:
```bash
kubectl describe node node-name
```

### Scale Deployment
Scale a deployment to a specific number of replicas:
```bash
kubectl scale deployment deployment-name --replicas=desired-replicas -n namespace-name
```

### Rollback Deployment
Rollback a deployment to the previous version:
```bash
kubectl rollout undo deployment/deployment-name -n namespace-name
```

### Check Deployment Status
Monitor the rollout status of a deployment:
```bash
kubectl rollout status deployment/deployment-name -n namespace-name
```

### Edit a Resource
Directly edit a resource in Kubernetes:
```bash
kubectl edit resource-type resource-name -n namespace-name
```

### Delete Namespace
Delete an entire namespace and its resources:
```bash
kubectl delete namespace namespace-name
```
