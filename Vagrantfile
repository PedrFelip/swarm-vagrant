# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  nodes = [
    {
      name: "master",
      ip: "192.168.56.10",
      memory: 1024,
      cpus: 1
    },
    {
      name: "node01",
      ip: "192.168.56.11",
      memory: 1024,
      cpus: 1
    },
    {
      name: "node02",
      ip: "192.168.56.12",
      memory: 1024,
      cpus: 1
    },
    {
      name: "node03",
      ip: "192.168.56.13",
      memory: 1024,
      cpus: 1,
    }
  ]

  config.vm.box = "centos/stream9"

  nodes.each do |node|
    config.vm.define node[:name] do |vm|
      vm.vm.hostname = node[:name]

      vm.vm.network "private_network", ip: node[:ip]


      vm.vm.provider "virtualbox" do |vb|
        vb.name = "Swarm-#{node[:name]}"
        vb.memory = node[:memory]
        vb.cpus = node[:cpus]
      end
    end
  end
end
