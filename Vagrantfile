Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/jammy64"

  servers = [
    { name: "Jenkins", ip: "192.168.56.14" },
    { name: "QA", ip: "192.168.56.15" },
    { name: "Prod", ip: "192.168.56.16" }
  ]

  servers.each do |server|
    config.vm.define server[:name] do |node|
      node.vm.hostname = server[:name]
      node.vm.network "private_network", ip: server[:ip]

      node.vm.provider "virtualbox" do |vb|
        vb.name = server[:name]
        vb.memory = 2048
        vb.cpus = 2
      end
    end
  end
end