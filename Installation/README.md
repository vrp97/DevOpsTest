# Installing required softwares

Here you will find the required details for installing required software on linux and their reference.


### Docker along with Git

Referred from [Here](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository)

```bash
sudo apt-get update
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo apt-key fingerprint 0EBFCD88
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
sudo docker run hello-world
```

Manage docker as non-root user, refer [this](https://docs.docker.com/engine/install/linux-postinstall/#manage-docker-as-a-non-root-user) , which can later useful for Jenkins pipeline with docker.


### Kubectl

Referred from [Here](https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-using-native-package-management)

```bash
sudo apt-get update && sudo apt-get install -y apt-transport-https gnupg2 curl
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee -a /etc/apt/sources.list.d/kubernetes.list
sudo apt-get update
sudo apt-get install -y kubectl
kubectl version --client
```


### Minikube

Referred from [Here](https://minikube.sigs.k8s.io/docs/start/#debian-package)

```bash
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube_latest_amd64.deb
sudo dpkg -i minikube_latest_amd64.deb
minikube version
```


### Helm

Referred from [Here](https://helm.sh/docs/intro/install/#from-apt-debianubuntu)

```bash
curl https://baltocdn.com/helm/signing.asc | sudo apt-key add -
sudo apt-get install apt-transport-https --yes
echo "deb https://baltocdn.com/helm/stable/debian/ all main" | sudo tee /etc/apt/sources.list.d/helm-stable-debian.list
sudo apt-get update
sudo apt-get install helm
helm version
```


### JDK

```bash
sudo apt install default-jdk
```


### Jenkins

Referred from [Here](https://www.jenkins.io/download/)

I have used standalone JAR file to run Jenkins locally

```bash
java -jar jenkins.war --httpPort=9090
```

### Azure CLI

You can refer [this link](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-apt#install-with-one-command) for installing Azure CLI in single step.


