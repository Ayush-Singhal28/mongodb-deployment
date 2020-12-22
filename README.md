#### Deploy Mongodb on K8

```bash
kubectl create ns database

cd charts
helm install mongodb ./mongodb-replicaset --namespace database
```

In order to check HA

Execute this script on another terminal
```bash
cd charts/mongodb-replicaset
./test.sh 
```

Delete the master pod. 


TO check HPA 
```bash
kubectl autoscale statefulset mongodb-mongodb-replicaset --cpu-percent=25  --min=3 --max=5 -n database

```