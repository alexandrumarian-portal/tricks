```
#Create a new pod with the name redis and with the image redis123.
#Use a pod-definition YAML file. And yes the image name is wrong!


controlplane ~ ➜  kubectl run redis --image=redis123 --dry-run=client -o yaml > redis-definition.yaml

controlplane ~ ➜  kubectl create -f redis-definition.yaml 
pod/redis created

controlplane ~ ➜  kubectl get pods
NAME            READY   STATUS         RESTARTS   AGE
nginx           1/1     Running        0          6m43s
newpods-p4vv6   1/1     Running        0          6m24s
newpods-pfd6k   1/1     Running        0          6m24s
newpods-nwf7k   1/1     Running        0          6m24s
redis           0/1     ErrImagePull   0          10s

controlplane ~ ✖ cat redis-definition.yaml 
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: null
  labels:
    run: redis
  name: redis
spec:
  containers:
  - image: redis123
    name: redis
    resources: {}
  dnsPolicy: ClusterFirst
  restartPolicy: Always
status: {}

controlplane ~ ➜  








```
