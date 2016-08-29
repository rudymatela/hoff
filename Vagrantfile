# This Vagrant box is intended for building final artifacts in an environment
# similar to the production environment (Ubuntu 16.04 in this case). This is to
# keep dependencies on dynamic libraries consistent. For local development, just
# using Stack should be fine.

# Note: when using the Virtualbox provider,
# run `vagrant plugin install vagrant-vboxguest` first.

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 575159689BEFB442
    echo 'deb http://download.fpcomplete.com/ubuntu xenial main' | sudo tee /etc/apt/sources.list.d/fpco.list
    sudo apt update
    sudo apt install -y ghc stack
  SHELL
end
