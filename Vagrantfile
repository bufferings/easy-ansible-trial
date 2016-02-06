Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"

  # Patch for https://github.com/mitchellh/vagrant/issues/6793
  # edit: Update so it doesn't error if you don't have Ansible installed.
  # In that case, you'll have to provision twice for this to work.
  config.vm.provision "shell" do |s|
    s.inline = '[[ ! -f $1 ]] || grep -F -q "$2" $1 || sed -i "/__main__/a \\    $2" $1'
    s.args = ['/usr/bin/ansible-galaxy', "if sys.argv == ['/usr/bin/ansible-galaxy', '--help']: sys.argv.insert(1, 'info')"]
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbook.yml"
  end
end
