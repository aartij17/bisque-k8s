This folder houses all the kubernetes artifacts required to deploy Persistent Volumes for BisQue. 

### PERSISTENT VOLUMES

Each Persistent Volume(PV) that is created to mount host data - requires a corresponding Persistent Volume Claim (PVC). 

In order to mount these PVs, please ensure that the `volumeMounts` and `volume` fields are populated in the `bisque-deployment.yaml`. These files define the storage class name `manual` which is created using `manual_storage_class.yaml`. 

Before creating the PVs, ensure that the data is present at the correct path in the host machine. 

To deploy, for each PV and PVC: 
```
kubectl create -f <name of the PV/PVC file>
```

### BISQUE DEPLOYMENT YAML
The `docker-compose.yaml` so far has consisted of 
the environment variables which are exported to serve the application. These variables can be moved to `bisque-deployment.yaml`. If you don't wish to do so, just remove the `env` field block in the `bisque-deployment.yaml` file. 

```
kubectl create -f bisque-deployment-yaml
```
