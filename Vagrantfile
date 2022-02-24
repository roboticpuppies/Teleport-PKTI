
Vagrant.configure("2") do |config|
  config.vm.network "public_network", bridge: "enp5s0"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "Ansible/playbook.yml"
  end
  config.vm.define "web-prod1" do |web1|
    web1.vm.box = "bento/ubuntu-20.04"
    web1.vm.hostname = "web-prod1.myra.my.id"
    web1.vm.provider "virtualbox" do |vweb1|
      vweb1.name = "web1"
      vweb1.cpus = 4
    end
  end

  config.vm.define "web-prod2" do |web2|
    web2.vm.box = "bento/ubuntu-20.04"
    web2.vm.hostname = "web-prod2.myra.my.id"
    web2.vm.provider "virtualbox" do |vweb2|
      vweb2.name = "web2"
      vweb2.cpus = 4
    end
  end

  config.vm.define "redis" do |redis|
    redis.vm.box = "bento/ubuntu-20.04"
    redis.vm.hostname = "redis.myra.my.id"
    redis.vm.provider "virtualbox" do |vredis|
      vredis.name = "redis"
      vredis.memory = 2048
      vredis.cpus = 2
    end
  end

  config.vm.define "db-prod" do |db|
    db.vm.box = "bento/ubuntu-20.04"
    db.vm.hostname = "db-prod.myra.my.id"
    db.vm.provider "virtualbox" do |vdb|
      vdb.name = "db-prod"
      vdb.memory = 2048
      vdb.cpus = 4
    end
  end
end