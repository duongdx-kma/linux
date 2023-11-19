Vagrant.configure("2") do |config|

  config.vm.define "scriptbox" do |scriptbox|
    scriptbox.vm.box = "geerlingguy/centos7"
  scriptbox.vm.network "private_network", ip: "192.168.56.78"
        scriptbox.vm.hostname = "scriptbox"
  scriptbox.vm.provider "virtualbox" do |vb|
     vb.memory = "1024"
  scriptbox.vm.synced_folder "./scriptbox_data", "/home/vagrant/vagrant_data", :mount_options => ["dmode=777", "fmode=666"]
   end
  end
  
  config.vm.define "web01" do |web01|
    web01.vm.box = "geerlingguy/centos7"
  web01.vm.network "private_network", ip: "192.168.56.79"
        web01.vm.hostname = "web01"
  end
  
  config.vm.define "web02" do |web02|
    web02.vm.box = "geerlingguy/centos7"
  web02.vm.network "private_network", ip: "192.168.56.80"
        web02.vm.hostname = "web02"
  end

   config.vm.define "db01" do |db01|
    db01.vm.box = "ubuntu/bionic64"
        db01.vm.network "private_network", ip: "192.168.56.81"
        db01.vm.hostname = "db01"
  end
end
