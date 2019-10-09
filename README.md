# ckad-helpers
Certified Kubernetes Appication Developer - Training Helpers

# Vagrant

*Before running `vagrant up`*, be sure to patch `./SOLUTIONS/s_02/k8sMaster.sh` with the included patch file (this makes `kubeadm init` advertise on the subnet that the minion VM can see).

The included `Vagrantfile` simplifies VM creation, but doesn't make it so simple you won't learn anything.

This will take you through the painful parts of lab 2.2, and you'll pick up manually at the "Configure the Master Node" heading. Be sure to understand the steps described in those early parts of lab 2.2, though.
