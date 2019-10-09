# ckad-helpers
Certified Kubernetes Appication Developer - Training Helpers

# Vagrant

The included `Vagrantfile` simplifies VM creation, but doesn't make it so simple you won't learn anything.

Before running `vagrant up`, be sure to patch `./SOLUTIONS/s_02/k8sMaster.sh` with the included patch file (this makes `kubeadm init` advertise on the subnet that the minion VM can see).
