Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/jammy64"
  
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "4096" 
    vb.cpus = 2
    vb.name = "gitmanager-dev"
  end

  config.vm.network "forwarded_port", guest: 80, host: 8080
  
  config.vm.synced_folder "./code", "/home/vagrant/code"
  
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update -y
    sudo apt-get upgrade -y
    
    sudo apt-get install -y wget
    wget https://packages.microsoft.com/config/ubuntu/22.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
    sudo dpkg -i packages-microsoft-prod.deb
    rm packages-microsoft-prod.deb
    sudo apt-get update
    sudo apt-get install -y dotnet-sdk-6.0
    
    sudo apt-get install -y libgdiplus libgl1
    
    sudo apt-get install -y git gitk git-gui
    
    sudo apt-get install -y sqlite3
    
    sudo apt-get install -y curl postgresql-client
    
    sudo apt-get autoremove -y
  SHELL
  
  config.vm.post_up_message = "Среда разработки готова! Используйте 'vagrant ssh' для подключения."
end