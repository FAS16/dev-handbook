# K8s Commands Cheat Sheet

## Restart Deployment/Pod Manually
```bash
kubectl rollout restart deployment <deployment-name>
```

## Get Pod logs 
(remove -f to not follow)
```bash
kubectl logs -f <pod-name>
```

## Get all Pods 
Use cases:
1. This will show you all pods in general.
2. Also shows this information READY, STATUS, RESTARTS, AGE
```bash
kubectl get pods
```


## "Describe" a pod
Provides detailed information about the pod's configuration, status, events, and lifecycle, including reasons for failures or restarts.
```bash
kubectl describe pod <pod-name>
```


## Get all Deployments
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
Use this to e.g. edit a configuration and then restart the deployment with the command above.
```bash
kubectl get configmaps
```

## Scale a Deployment 
(N=Number of pods, 0 is effectively stopping the application entirely)
```bash
kubectl scale deployment <deployment-name> --replicas=N
```

## Get and decode Secret
This command retrieves the Kubernetes secret in JSON format, decodes each base64-encoded value within its .data field using jq, and outputs the result as a readable JSON object.
```bash
kubectl get secret <secret-name> -o json | jq '.data | map_values(@base64d)'
```

## Template
```bash
your-command-here
```
