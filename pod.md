### Create Pod without yaml
new pod called nginx, using image from Dockerhub 'nginx'
``` k run nginx --image=nginx ```

### Which node are the pods running
you can "describe" all pods one by one, or,
``` k get pods -o wide ```

### Create Pod using yaml

either create the yaml from scratch, or, use "dry-run"

```
k run redis --image=redis --dry-run=client -o yaml > redis.yaml
```

``` yaml

apiVersion: v1
kind: Pod
metadata:
  name: nginx
  labels:
    app: nginx
    tier: frontend
spec:
  containers:
  - name: nginx
    image: nginx

```

commands to use pod yaml:

```
k apply -f pod.yaml
k get pods
k describe pods nginx
k delete pod nginx
```