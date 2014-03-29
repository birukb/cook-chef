VAGRANTFILE_API_VERSION = "2"

server_box_name = "opscode_centos-6.4_chef-11.4.4"
server_box_url  = "https://opscode-vm.s3.amazonaws.com/vagrant/opscode_centos-6.4_chef-11.4.4.box"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.omnibus.chef_version = :latest
  config.vm.box = server_box_name
  config.vm.box_url = server_box_url
  config.vm.network :private_network, ip: '192.168.250.32'
    
  config.vm.provision :chef_client do |chef|
    chef.provisioning_path = "/etc/chef"
    chef.chef_server_url = "https://api.opscode.com/organizations/bir"
    chef.validation_key_path = "../.chef/bir-validator.pem"
    chef.validation_client_name = "bir-validator"
    chef.node_name = "my_node"
  end
end
