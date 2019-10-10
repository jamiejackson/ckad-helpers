# ckad-helpers
Certified Kubernetes Appication Developer - Training Helpers

# Lab 2.2

## Vagrant

The included `Vagrantfile` simplifies VM creation, but doesn't make it so simple you won't learn anything.

*Before running `vagrant up`*, be sure to patch `./SOLUTIONS/s_02/k8sMaster.sh` with the included patch file (this makes `kubeadm init` advertise on the subnet that the minion VM can see).

This will take you through the otherwise painful parts of lab 2.2, and you'll pick up manually at the "Configure the Master Node" heading. Be sure to understand the steps described in those early parts of lab 2.2, though.

*CEP Notes:*
  * The following will add the vagrant user to the docker group and allow accessing the commands from the vagrant user:
```
sudo usermod -aG docker $USER
source ~/.bashrc
sudo cp /root/.kube /home/vagrant/.
sudo chown -R vagrant .kube  
```
  
# Lab 2.3

  * Step 7 - Watch the `kubectl get pod -o wide` command - the demo shows the pod being created on node `ckad-1`, while the command may display it on `ckad2`.
  * Step 13 - Run the `curl` command against the Master node IP address: i.e. `curl http://192.167.50.77:{{port from step 12}}`
