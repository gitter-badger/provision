Vagrant::Config.run do |config|
  config.vm.forward_port 80, 8080
end

Vagrant.configure('2') do |config|
  config.vm.provider :virtualbox do |vb|
    vb.customize ['modifyvm', :id, '--memory', '512']
    vb.customize ['modifyvm', :id, '--cpus', '2']
    vb.customize ['modifyvm', :id, '--ioapic', 'on']
  end

  config.vm.define :vagrant_demo_server do |service_config|
    service_config.vm.box = 'precise64'
    service_config.vm.box_url = 'http://files.vagrantup.com/precise64.box'
    service_config.vm.network :private_network, ip: '192.168.100.33'
  end
end
