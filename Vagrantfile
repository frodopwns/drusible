Vagrant.configure("2") do |config|
  config.vm.box = "precise32"
  config.vm.box_url = "http://files.vagrantup.com/precise32.box"
  config.vm.hostname = "drupallocal"
  config.vm.network :private_network, ip: "192.168.33.15"
  config.vm.synced_folder("data", "/data")

  # add a bit more memory, it never hurts. It’s VM specific and we’re using Virtualbox here.
  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", 2048]
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
    ansible.sudo = true
    ansible.host_key_checking = false
    ansible.extra_vars = { ansible_ssh_user: 'vagrant',
                           ansible_connection: 'ssh',
                           ansible_ssh_args: '-o ForwardAgent=yes'}
  end
end
