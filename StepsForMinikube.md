# K8 Minikube Steps

- winget install minikube
- minikube start --vm / minikube start --driver=docker/virtualbox
- kubectl cluster-info
- mkdir kube - [usually in app folder]
- write k8 yaml files in it [Deployemnt, Services]
- kubectl explain deployment [The kubectl explain command can print the specification of every Kubernetes resource directly in your terminal]
- kubectl explain deployment.spec.replicas [To drill down to a specific field use]
- minikube status
- kubectl apply -f kube [kube- folder name where k8 config files reside]
- kubectl get pods --watch
- minikube tunnel [For accessing LoadBalancer service]
- kubectl get services [service name (optional)] - [Get url of the service]
- [OR] minikube service knote --url
- kubectl delete -f kube [kube- folder name where k8 config files reside]
