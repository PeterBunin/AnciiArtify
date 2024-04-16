# Overview
There are a few tools that claim to (partially) replace a fully fledged Kubernetes cluster. Using them allows e.g. every developer to have their own local cluster instance running to play around with it, deploy their application or execute tests against applications running in K8s during CI/CD. Lets have a look at three of them, compare their pros and cons and identify use cases for each of them.

|       | minikube  | kind  | k3d |
|---    |---        |---    |---
| supported architectures	|   AMD64   |   AMD64	|   AMD64, ARMv7, ARM64
| supported container runtimes	| Docker,CRI-O,containerd,gvisor    | Docker    | Docker, containerd
| startup time initial/following	|5:19 / 3:15|	2:48 / 1:06	|0:15 / 0:15|
| memory requirements |	2GB |	8GB |   512 MB| 
| multi-node support |	no | yes |  yes |

# **Minikube** 
Easy to install on GitHub codespases for local testing

````
minikube start
````

# **kind (Kubernetes IN Docker)**

Easy to install with go

````
go install sigs.k8s.io/kind@v0.22.0
kind create cluster
````

# **k3d**

Easy to install with curl

````
curl -s https://raw.githubusercontent.com/k3d-io/k3d/main/install.sh | bash
k3d cluster create three-node-cluster --agents 3
````
# Demo
