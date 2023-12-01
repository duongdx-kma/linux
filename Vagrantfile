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

  #start: docker engine
  config.vm.define "docker" do |docker|
    docker.vm.box = "ubuntu/bionic64"
    docker.vm.network "private_network", ip: "192.168.56.88"
    docker.vm.hostname = "docker"
    docker.vm.synced_folder "./docker_data", "/home/vagrant/docker_data", :mount_options => ["dmode=777", "fmode=666"]
    
    docker.vm.provider "virtualbox" do |vb|
      # Customize the amount of memory on the VM:
      vb.memory = "2048"
      vb.cpus = "2"
    end
  end
  #end: docker engine
  
  #start: terraform
  config.vm.define "terraform" do |terraform|
    terraform.vm.box = "geerlingguy/centos7"
    terraform.vm.network "private_network", ip: "192.168.56.89"
    terraform.vm.hostname = "terraform"
    terraform.vm.synced_folder "./terraform_data", "/home/vagrant/terraform_data", :mount_options => ["dmode=777", "fmode=666"]

    terraform.vm.provider "virtualbox" do |vb|
      # Customize the amount of memory on the VM:
      vb.memory = "2048"
      vb.cpus = "2"
    end
  end
  #end: terraform engine

end
