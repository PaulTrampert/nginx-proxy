Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"

  config.vm.provision "ansible", run: "always" do |ansible|
    ansible.playbook = "tests/test.yml"
  end
end
