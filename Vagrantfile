Vagrant.configure("2") do |config|
  config.vm.box = "debian12-docker-dapw-ud5"

  # 5 nodos (3 managers + 2 workers)
  nodes = {
    "manager1" => "192.168.57.10",
    "manager2" => "192.168.57.11",
    "manager3" => "192.168.57.12",
    "worker1" => "192.168.57.20",
    "worker2" => "192.168.57.21",
  }

  nodes.each do |name, ip|
    config.vm.define name do |node|
      node.vm.hostname = name
      node.vm.network "private_network", ip: ip
      
      node.vm.provider "virtualbox" do |vb|
        vb.memory = "1024" # 1GB RAM por nodo
        vb.cpus = 1 # 1 CPU por nodo
      end
    end
  end
end