Vagrant.configure("2") do |config|
config.hostmanager.enable = true
config.vm.box = "ubuntu/trusty64"
config.vm.network "public_network"
config.vm.synced_folder "vpro_app","/root"

################################# INSTALLING CI_SERVER #############################
      
         config.vm.define "ci" do |build|
         build.vm.hostname = 'build.com'
         build.vm.network "private_network", ip: "192.168.10.11"
         build.vm.provision "shell", inline: <<-SHELL

          cd /root
           ./ciserver.sh
         
         SHELL
end
##################################### INSTALLING APPSERVER ##############################

         config.vm.define "app" do |build|
         build.vm.hostname = 'app.com'
         build.vm.network "private_network", ip: "192.168.10.12"
         build.vm.provision "shell", inline: <<-SHELL

          cd /root
           ./appserver.sh
         
         SHELL
end

###################################  INSTALLING MYSQL  ###############################

         config.vm.define "db" do |build|
         build.vm.hostname = 'db.com'
         build.vm.network "private_network", ip: "192.168.10.13"
         build.vm.provision "shell", inline: <<-SHELL

          cd /root
           ./mysql.sh
         
         SHELL
end
#################################### INSTALLING LB ########################################

         config.vm.define "lb" do |build|
         build.vm.hostname = 'lb.com'
         build.vm.network "private_network", ip: "192.168.10.14"
         build.vm.provision "shell", inline: <<-SHELL

          cd /root
           ./lb.sh
         
         SHELL
end
############################### INSTALLING MEMCACHE #########################################

         config.vm.define "mem" do |build|
         build.vm.hostname = 'mem.com'
         build.vm.network "private_network", ip: "192.168.10.15"
         build.vm.provision "shell", inline: <<-SHELL

          cd /root
           ./mem.sh
         
         SHELL
end
########################### INSTALLING RABBITMQ ###########################################
        
         config.vm.define "rmq" do |build|
         build.vm.hostname = 'rmq.com'
         build.vm.network "private_network", ip: "192.168.10.16"
         build.vm.provision "shell", inline: <<-SHELL

          cd /root
           ./rmq.sh
         
         SHELL
end
end
