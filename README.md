#deleted docker-compose, Dockerrun & .travis (rewrite eventually)
#deleted nginx dir b/c of the utilization of ingress service of k8s

#can use "kubectl apply -f <dir>" - for all config files within a dir


#need volumes for dbs b/c data isn't persistent in pod alone
#volume --> object that allows a container to store data @ pod level
 - data can persist container restarts, but not pods'
#persistent volume --> object storage that lives outside of pods; not tied to any one pod
 - data can persist both container & pod restarts
#persistent volume claim --> "billboard"; an advertisement
 - resource that is attached to pod config file (k8s "salesman" will statically or dynamically deliver such volume
#access modes: ReadWriteOnce (one node), ReadOnlyMany, ReadWriteMany

#options k8s has to create persistent volume based on claim
kubectl get storageclass
 - take portion of hd/vhd of node or block store, file, disk of cloud provider

#persistent volume & claim info
kubectl get pv(c)

#secrets object - securely store piece of info in cluster, like passwords
kubectl create secret <secret_type> <secret_name> --from-literal key=value
kubectl get secrets

#loadbalancer (old) --> ingress
 - exposes a set of services to outside world

#ingress-nginx; NOT kubernetes-ingress
 - ingress is like deployment object; declarative; config creates controller
 - will create a pod running nginx that handles routing 
