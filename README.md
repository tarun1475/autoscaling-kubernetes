# Install-Kubernetes-on-CentOs

## Configure Master node

Follow commands in [master.sh](https://github.com/tarun1475/autoscaling-kubernetes/blob/master/master.sh)

## Configure Slave node

Follow commands in [slave.sh](https://github.com/tarun1475/autoscaling-kubernetes/blob/master/slave.sh)

## Create the yaml files for:

- Pod [pod.yaml](https://github.com/tarun1475/autoscaling-kubernetes/blob/master/pod.yaml)
- Service [service.yaml](https://github.com/tarun1475/autoscaling-kubernetes/blob/master/service.yaml)
- Deployment [deployment.yaml](https://github.com/tarun1475/autoscaling-kubernetes/blob/master/deployment.yaml)
- Replication Controller [replicationController.yaml](https://github.com/tarun1475/autoscaling-kubernetes/blob/master/replicationController.yaml)
- api [api.yaml](https://github.com/tarun1475/autoscaling-kubernetes/blob/master/api.yaml)
  To check nodes

```
kubectl get nodes
```

To check the pod

```
kubectl get pods
```

To get information about pod

```
kubectl describe pod pod
```

## Configure the node for Horizontal Pod Autoscaling

### Create the following yaml files

- Heapster [heapster.yaml](https://github.com/tarun1475/autoscaling-kubernetes/blob/master/heapster.yaml)
- hpa [hpa.yaml](https://github.com/tarun1475/autoscaling-kubernetes/blob/master/hpa.yaml)
- custom metrics [./metrics-server](https://github.com/tarun1475/autoscaling-kubernetes/tree/master/metrics-server)
- metrics [custom-metrics.yaml](https://github.com/tarun1475/autoscaling-kubernetes/blob/master/metrics/custom-metrics.yaml)

## Check the HPA

```
kubectl describe hpa hpaName
```

## Check the scaling using busy box

```
   kubectl run -i --tty load-generator --image=busybox /bin/sh

   while true; do wget -q -O- IPAddress:PortANumber; done

```
