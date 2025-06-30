# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # Выбор базового образа (Ubuntu 22.04 LTS)
  config.vm.box = "ubuntu/jammy64"
  
  # Выделение ресурсов
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "4096" # 4GB RAM
    vb.cpus = 2
    vb.name = "gitmanager-dev"
  end

  # Проброс портов (если нужно)
  config.vm.network "forwarded_port", guest: 80, host: 8080
  
  # Синхронизация папок
  config.vm.synced_folder "./code", "/home/vagrant/code"
  
  # Автоматическая настройка окружения
  config.vm.provision "shell", inline: <<-SHELL
    # Обновление пакетов
    sudo apt-get update -y
    sudo apt-get upgrade -y
    
    # Установка .NET 6+
    sudo apt-get install -y wget
    wget https://packages.microsoft.com/config/ubuntu/22.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
    sudo dpkg -i packages-microsoft-prod.deb
    rm packages-microsoft-prod.deb
    sudo apt-get update
    sudo apt-get install -y dotnet-sdk-6.0
    
    # Установка зависимостей для Avalonia
    sudo apt-get install -y libgdiplus libgl1
    
    # Установка Git и инструментов разработки
    sudo apt-get install -y git gitk git-gui
    
    # Установка SQLite
    sudo apt-get install -y sqlite3
    
    # Дополнительные инструменты (опционально)
    sudo apt-get install -y curl postgresql-client
    
    # Очистка кеша
    sudo apt-get autoremove -y
  SHELL
  
  # Настройки после провижининга
  config.vm.post_up_message = "Среда разработки готова! Используйте 'vagrant ssh' для подключения."
end