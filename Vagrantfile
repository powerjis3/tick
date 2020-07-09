box = "generic/ubuntu1804"

Vagrant.configure("2") do |config|

  config.vm.define "web" do |web|
    web.vm.box = box
    web.vm.hostname = "web"

    web.vm.network "private_network", ip: "192.168.69.11", virtualbox__intnet: "tick"

    web.vm.provider "virtualbox" do |v|
      v.name = "web"
      v.memory = 1024
      v.cpus = 1
      ## change vga controller default(VBoxVGA) to VMSVGA
      ## virtualbox says that "Invalid settings detected"
      v.customize ["modifyvm", :id, "--graphicscontroller", "vmsvga"]
    end
  end

  config.vm.define "grafana" do |grafana|
    grafana.vm.box = box
    grafana.vm.hostname = "grafana"

    grafana.vm.network "private_network", ip: "192.168.69.12", virtualbox__intnet: "tick"

    grafana.vm.provider "virtualbox" do |v|
      v.name = "grafana"
      v.memory = 1024
      v.cpus = 1
      v.customize ["modifyvm", :id, "--graphicscontroller", "vmsvga"]
    end
  end

  config.vm.define "influxdb01" do |influxdb01|
    influxdb01.vm.box = box
    influxdb01.vm.hostname = "influxdb01"

    influxdb01.vm.network "private_network", ip: "192.168.69.13", virtualbox__intnet: "tick"

    influxdb01.vm.provider "virtualbox" do |v|
      v.name = "influxdb01"
      v.memory = 2048
      v.cpus = 2
      v.customize ["modifyvm", :id, "--graphicscontroller", "vmsvga"]
    end
  end

  config.vm.define "influxdb02" do |influxdb02|
    influxdb02.vm.box = box
    influxdb02.vm.hostname = "influxdb02"

    influxdb02.vm.network "private_network", ip: "192.168.69.14", virtualbox__intnet: "tick"

    influxdb02.vm.provider "virtualbox" do |v|
      v.name = "influxdb02"
      v.memory = 2048
      v.cpus = 2
      v.customize ["modifyvm", :id, "--graphicscontroller", "vmsvga"]
    end
  end
end
