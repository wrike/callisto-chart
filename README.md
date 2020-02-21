# Callisto

Callisto is an open-source Kubernetes-native implementation of [Selenium Grid](https://en.wikipedia.org/wiki/Selenium_(software)).

See [this repository](https://github.com/wrike/callisto) for the source code.


### How to run in Docker for Mac
1. Install [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) & [helm](https://helm.sh/docs/intro/install/)
2. Enable Kubernetes in [Docker for Mac](https://docs.docker.com/docker-for-mac/#kubernetes)
3. Install [Ingress Controller](https://github.com/kubernetes/ingress-nginx/blob/master/docs/deploy/index.md#prerequisite-generic-deployment-command)
4. Install callisto: 

`helm template . | kubectl apply -f -`

5. Add corresponding line to the bottom of /etc/hosts:

`localhost callisto.local`

### How to run in minikube
1. Install [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) & [helm](https://helm.sh/docs/intro/install/)
2. Install [minikube](https://kubernetes.io/docs/setup/learning-environment/minikube/)
3. Enable  [Ingress Controller](https://github.com/kubernetes/ingress-nginx/blob/master/docs/deploy/index.md#minikube)
4. Install callisto:

`helm template . | kubectl apply -f -`  

5. Get external minikube ip:

```minikube ip```

6. Add corresponding line to the bottom of **/etc/hosts**:

`<minikube.external.ip> callisto.local`


### How to access callisto features

1. To open Selenoid UI use:

`http://callisto.local`

2. To run your tests use the same url:

`http://callisto.local`

### How to run as helm release

1. To install the chart with the release name callisto:

`helm install --name callisto .`

2. To uninstall release:

`helm delete callisto`
