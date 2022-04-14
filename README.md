# how-to-kinD
## quick start
### install
```
brew install kind
```

### create a cluster
```
kind create cluster # Default cluster context name is `kind`
...
kind create cluster --name apache-airflow
kind create cluster --name apache-spark
```

### list cluster
```
kind get clusters
```

### delete cluster
```
kind delete cluster 

# if the flag `--name` is not specified, kind will use the default cluster context name `kind` and delete that cluster


kind delete cluster --name apache-airflow

```

### configuring kind cluster + create cluster from a config file
```
kind create cluster --config kind-example-config.yaml
```
```
# three node (two workers) cluster config
# kind-example-config.yaml

kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
- role: worker
- role: worker
- role: worker
```