11 config files; 5 deployments, 4 clusterip services, ingress service, postgres PVC
worker & redis share clusterip service

Pods -> runs one or more closely related containers
Services -> sets up networking in a k8s cluster
 - ClusterIP -> exposes a set of pods to other objects in cluster
 - NodePort -> exposes a set of pods to outside world
  - port (OTHER pods that needs this pod), targetPort (port of target pod), nodePort (port we have access to)

can combine config files by separating them with "---"
