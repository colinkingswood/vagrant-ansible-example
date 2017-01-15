VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/zesty64"

  config.vm.network "forwarded_port", guest: 80, host: 8083  # 80 is the vagrant box, 8083 is the actaul laptip port
  config.vm.provision :shell, path: "install_python.sh"      # need this for ansible to work
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook.yml"
  end
end
