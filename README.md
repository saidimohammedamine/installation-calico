# installation-calico               

first 1. Ensure Prerequisites : Before installing Calico, ensure:

-You have a Kubernetes cluster initialized with kubeadm

-Your nodes are in Ready state (kubectl get nodes)

-The kubectl command is configured properly


2. Disable Swap : 
               
        -sudo swapoff -a
        -sudo sed -i '/ swap / s/^/#/' /etc/fstab


               3. Install Calico :
  Run the following command to apply the Calico manifest:

        -kubectl apply -f https://docs.projectcalico.org/manifests/calico.yaml
-This will:

+Deploy Calico components as Kubernetes pods in the kube-system namespace.

+Configure networking between nodes.

  4. Verify Installation : 
  Check that the Calico pods are running:

          - kubectl get pods -n kube-system
  
- Expected output:

NAME                                       READY   STATUS    RESTARTS   AGE
calico-kube-controllers-xxxxxx             1/1     Running   0          Xs
calico-node-xxxxx                          1/1     Running   0          Xs
calico-typha-xxxxx                         1/1     Running   0          Xs




                  - 
