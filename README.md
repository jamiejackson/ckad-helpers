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

# Chapter 3:
 Terms:
 * 3.6 - _protobuf_ - Protocol Buffers - Protocol buffers are Google's language-neutral, platform-neutral, extensible mechanism for serializing structured data – think XML, but smaller, faster, and simpler. You define how you want your data to be structured once, then you can use special generated source code to easily write and read your structured data to and from a variety of data streams and using a variety of languages.  (https://developers.google.com/protocol-buffers)
 
 Labs:
 * 3.2.18 - I don't understand the changes needed.  This seems to be old.  I skipped this and moved on the step 19, and everything worked as expected.
 * 3.2.21 - Use the IP address from step `3.2.20` for the *CLUSTER_IP* of `service/registry`
 * 3.2.22 - Use the same IP and just add it to the existing `daemon.json` file - append it to the end as a separate struct.. 
       
