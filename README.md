# ckad-helpers
Certified Kubernetes Appication Developer - Training Helpers

# Lab 2.2

## Vagrant

The included `Vagrantfile` simplifies VM creation, but doesn't make it so simple you won't learn anything.

*Before running `vagrant up`*, be sure to patch `./SOLUTIONS/s_02/k8sMaster.sh` with the included patch file (this makes `kubeadm init` advertise on the subnet that the minion VM can see).

This will take you through the otherwise painful parts of lab 2.2, and you'll pick up manually at the "Configure the Master Node" heading. Be sure to understand the steps described in those early parts of lab 2.2, though.
