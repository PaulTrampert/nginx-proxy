Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"

  config.vm.provision "shell", run: "always", inline: "sudo rm -rf /usr/share/ansible/roles/nginx-proxy || true && sudo mkdir -p /usr/share/ansible/roles && sudo cp -r /vagrant /usr/share/ansible/roles/nginx-proxy"

  config.vm.provision "ansible_local", run: "always" do |ansible|
    ansible.playbook = "tests/test.yml"
    ansible.galaxy_role_file = "requirements.yml"
    ansible.galaxy_roles_path = "/usr/share/ansible/roles"
    ansible.galaxy_command = "sudo ansible-galaxy install --role-file=%{role_file} --roles-path=%{roles_path} --force"
  end
end
