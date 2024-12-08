# Kubectl Cheat Sheet

[K8s snippets](cheatsheets/snippets/k8s)

#### Get Eventstream of namespace
  `kubectl get events -w -n <namespace>`

#### Get Endpoints in namespace
  `kubectl get endpoints -n <namespace>`

#### Rollout Restatr
  `kubectl rollout restart RESOURCE`
  
#### Exec

#### Port-forward 

 - to a pod

    `kubectl -n \<namespace\> port-forward pod/\<pod-name\> \<local-port\>:\<pod-port\>`
      
 - to a service
   
    `kubectl -n \<namespace\> port-forward service/\<service-name\> \<local-port\>:\<pod-port\>`

#### Service DNS naming
 
 \<servicename\>.\<namespace\>.svc.cluster.local
 
### Drain and Uncordon
    
   `kubectl drain \<Node\> --ignore-daemonsets --delete-emptydir-data --force`

   `kubectl uncordon \<Node\>`
 
### Node selector and labels

  - Label nodes
  
  `kubectl label nodes \<Node\> storage=ssd`
  
  - Delete node label
  
  `kubectl label nodes minion1 storage-`
  
  - Get node labels
  
  `kubectl get node kind-worker -o json | jq '.metadata.labels'`
  
  - Node selector
  ```
  kind: Pod
  ...
  spec:
    containers:
    - 
      ...
    nodeSelector:
      storage: ssd
  ```
  
## Troubleshooting
- stern (https://github.com/stern/stern)

    `stern . -n kube-system --tail 0`

- Curl
    - -i, --include       Include protocol response headers in the output
    - -k, --insecure      Allow insecure server connections when using SSL
    - -L, --location      Follow redirects
    - Run Curl every X seconds: `while -n \<X-seconds\> \<cmd\>`
