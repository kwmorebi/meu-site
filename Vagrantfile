Vagrant.configure("2") do |config|

  config.vm.box = "cloud-image/debian-13"
  config.vm.box_version = "20260501.2465.0"
  config.vm.box_check_update = false


  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 22, host: 2222, id: "ssh"

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.network "private_network", ip: "192.168.0.2"

  config.vm.synced_folder "./meu-site", "/var/www/meu-site"

  # Disable the default share of the current code directory. Doing this
  # provides improved isolation between the vagrant box and your host
  # by making sure your Vagrantfile isn't accessible to the vagrant box.
  # If you use this you may want to enable additional shared subfolders as
  # shown above.
  # config.vm.synced_folder ".", "/vagrant", disabled: true

 
  config.vm.provider "virtualbox" do |vb|
  vb.name = "VM-Ativ-Vagrant"
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #   # Customize the amount of memory on the VM:
     vb.memory = "1024"
  end


  # Enable provisioning with a shell script. Additional provisioners such as
  # Ansible, Chef, Docker, Puppet and Salt are also available. Please see the
  # documentation for more information about their specific syntax and use.
  config.vm.provision "shell", inline: <<-SHELL
     apt-get update
     apt-get install -y apache2

     chmod -R 755 /var/www/meu-site
     rm -rf /var/www/html
     ln -s /var/www/meu-site /var/www/html
  SHELL
  end
