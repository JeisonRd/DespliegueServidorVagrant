# Vagrantfile
Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/bionic64"
  
    # Configuración de la primera máquina virtual
    config.vm.define "web1" do |web1|
      web1.vm.network "private_network", ip: "192.168.56.10"
      web1.vm.synced_folder "./html", "/var/www/html"
      web1.vm.provision "shell", inline: <<-SHELL
        apt-get update
        apt-get install -y apache2
        systemctl enable apache2
        systemctl start apache2
      SHELL
    end
  
    # Configuración de la segunda máquina virtual
    config.vm.define "web2" do |web2|
      web2.vm.network "private_network", ip: "192.168.56.11"
      web2.vm.synced_folder "./html", "/var/www/html"
      web2.vm.provision "shell", inline: <<-SHELL
        apt-get update
        apt-get install -y apache2
        systemctl enable apache2
        systemctl start apache2
      SHELL
    end
  end
  