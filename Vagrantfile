Vagrant.configure("2") do |config|
  
  config.vm.box = "ubuntu/bionic64"
  
  config.vm.define "ckad1" do |machine|
    machine.vm.hostname = "ckad1"
    machine.vm.network "private_network", ip: "192.168.50.77"
    
    machine.vm.provision "setup_k8s_master",
       type: "shell",
       path: "SOLUTIONS/s_02/k8sMaster.sh"
  end

  config.vm.define "ckad2" do |machine|
    machine.vm.hostname = "ckad2"
    machine.vm.network "private_network", ip: "192.168.50.78"

    machine.vm.provision "setup_k8s_second",
       type: "shell",
       path: "SOLUTIONS/s_02/k8sSecond.sh"
  end
  
  # https://kubernetes.io/docs/setup/production-environment/container-runtimes/#docker
  config.vm.provision "setup_container_runtime",
    type: "shell",
    inline: <<-SHELL
      set -x
      mkdir -p /etc/docker
      echo '
        {
          "exec-opts": ["native.cgroupdriver=systemd"],
          "log-driver": "json-file",
          "log-opts": {
            "max-size": "100m"
          },
          "storage-driver": "overlay2"
        }
        ' > /etc/docker/daemon.json
    SHELL
  
  # allow guests to reach each other by hostname
  config.vm.provision "allow_guest_host_resolution",
    type: "shell",
    inline: <<-SHELL
    set -x
    apt-get install -y avahi-daemon libnss-mdns
  SHELL
  
end
