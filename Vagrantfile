Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/xenial64"

    config.vm.network "private_network", type: "dhcp"
    config.vm.synced_folder "src/", "/var/www/html/"
    config.vm.network :forwarded_port, guest: 7070, host: 80, auto_correct: true
    config.vm.network :forwarded_port, guest: 2222, host: 22, auto_correct: true

    config.vm.provision "shell" do |s|
        s.inline = "apt-get update && apt-get install -y python"
    end

    config.vm.provision :shell, path: "./playbooks/ansible_install.sh"

    config.vm.provision "ansible" do |ansible|
        ansible.playbook = "playbooks/policy.yml"
        ansible.playbook = "playbooks/bootstrap.yml"
        ansible.playbook = "playbooks/httpd.conf"
        ansible.playbook = "playbooks/php.conf"
        ansible.playbook = "playbooks/ssl.conf"
    end
end