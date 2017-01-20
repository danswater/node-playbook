# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

	config.vm.box = "ubuntu/trusty64"

	config.vm.define "machine", primary: true do |machine|
		machine.vm.provision "ansible" do |ansible|
			ansible.playbook   = "provisioning/playbook.yml"
			ansible.extra_vars = { ansible_ssh_user: "vagrant" }
			ansible.verbose    = "vvvv"
			ansible.groups     = {
				"app" => [ "machine" ]
			}
		end
	end
end
