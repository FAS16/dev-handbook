# K8s Commands Cheat Sheet

## Restart Pod Manually
```bash
kubectl rollout restart deployment <deployment-name>
```

## See Pod logs 
(remove -f to not follow)
```bash
kubectl logs -f <pod-name>
```
x
## See all Pods 
```bash
kubectl get pods
```

## See all Deployments
```bash
kubectl get deployments
```

## Remove a deployment
This will all associated ReplicaSets and Pods managed by it. For verification do kubectl get deployments, pods, replicasets
```bash
kubectl delete deployment <deployment-name>
```

## Get ConfigMaps
```bash
kubectl edit configmap <config-map-name>
```

## Edit ConfigMaps
```bash
kubectl get configmaps
```

## Scale a Deployment 
(N=Number of pods, 0 is effectively stopping the application entirely)
```bash
kubectl scale deployment <deployment-name> --replicas=N
```

## Template
```bash
your-command-here
```
