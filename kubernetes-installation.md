### Install Docker ###
yum install docker

service docker start

systemctl enable docker

docker run hello-world


### Copy kubernetes.repo to /etc/yum.repos.d/kubernetes.repo ###
cp kubernetes.repo /etc/yum.repos.d/kubernetes.repo

### Copy k8s.conf to /etc/sysctl.d/k8s.conf ###
cp k8s.conf /etc/sysctl.d/k8s.conf 

### Disable SELinux
 setenforce 0

### install kubelet, kubeadm and kubectl; start kubelet daemon
### Do it on both master as welll as worker nodes

    yum install -y kubelet kubeadm kubectl --disableexcludes=kubernetes

### persist kubelet kubeadm kubectl ###
