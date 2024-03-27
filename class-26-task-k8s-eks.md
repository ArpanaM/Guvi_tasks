# Create the K8s EKS,further you have to do the deployment of Nginx application

# install eksctl and kubectl


# Create cluster

![image](https://github.com/ArpanaM/Guvi_tasks/assets/68733492/7609fedc-a972-4ef5-8035-11b254227143)

# Cluster Created

![image](https://github.com/ArpanaM/Guvi_tasks/assets/68733492/f75991b2-fd5e-4c7c-aea3-b4e26cee0c8e)


# 2 default nodes are created
![image](https://github.com/ArpanaM/Guvi_tasks/assets/68733492/9d28a393-785c-444f-af15-24b219dd82bc)


# EKS
![image](https://github.com/ArpanaM/Guvi_tasks/assets/68733492/dca7adec-49ac-4e1c-b60e-1d08139de784)

# created Pod.Yaml file
![image](https://github.com/ArpanaM/Guvi_tasks/assets/68733492/95455c5e-5195-452b-821b-6bb8e162be10)

# Execcuted pod.yaml file

![image](https://github.com/ArpanaM/Guvi_tasks/assets/68733492/ea354711-acda-4202-bdf6-eeffd2d19846)

# Pods are running

![image](https://github.com/ArpanaM/Guvi_tasks/assets/68733492/e49aafbe-8157-49bc-9865-aa96b248465e)

![image](https://github.com/ArpanaM/Guvi_tasks/assets/68733492/207f325d-1714-4cc0-a77e-293534723695)

ubuntu@ip-172-31-28-30:~$ kubectl describe pod mypod
Name:         mypod
Namespace:    default
Priority:     0
Node:         ip-192-168-38-62.ec2.internal/192.168.38.62
Start Time:   Wed, 27 Mar 2024 10:17:33 +0000
Labels:       app=web
Annotations:  <none>
Status:       Running
IP:           192.168.44.246
IPs:
  IP:  192.168.44.246
Containers:
  mycontainer:
    Container ID:   containerd://42ea7946d311cbef6c5e65e021380acb37223ee3d90f99b287bd4a651493d997
    Image:          nginx
    Image ID:       docker.io/library/nginx@sha256:6db391d1c0cfb30588ba0bf72ea999404f2764febf0f1f196acd5867ac7efa7e
    Port:           80/TCP
    Host Port:      0/TCP
    State:          Running
      Started:      Wed, 27 Mar 2024 10:17:38 +0000
    Ready:          True
    Restart Count:  0
    Environment:    <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-zhlbx (ro)
Conditions:
  Type                        Status
  PodReadyToStartContainers   True 
  Initialized                 True 
  Ready                       True 
  ContainersReady             True 
  PodScheduled                True 
Volumes:
  kube-api-access-zhlbx:
    Type:                    Projected (a volume that contains injected data from multiple sources)
    TokenExpirationSeconds:  3607
    ConfigMapName:           kube-root-ca.crt
    ConfigMapOptional:       <nil>
    DownwardAPI:             true
QoS Class:                   BestEffort
Node-Selectors:              <none>
Tolerations:                 node.kubernetes.io/not-ready:NoExecute op=Exists for 300s
                             node.kubernetes.io/unreachable:NoExecute op=Exists for 300s
Events:
  Type    Reason     Age   From               Message
  ----    ------     ----  ----               -------
  Normal  Scheduled  13m   default-scheduler  Successfully assigned default/mypod to ip-192-168-38-62.ec2.internal
  Normal  Pulling    13m   kubelet            Pulling image "nginx"
  Normal  Pulled     13m   kubelet            Successfully pulled image "nginx" in 4.299s (4.299s including waiting)
  Normal  Created    13m   kubelet            Created container mycontainer
  Normal  Started    13m   kubelet            Started container mycontainer

