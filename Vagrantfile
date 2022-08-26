VAGRANTFILE_API_VERSION = "2"
box      = 'jenkins/jenkins'
url      = 'https://atlas.hashicorp.com/ubuntu/boxes/trusty64'
hostname = 'jenkins'
ip       = '192.168.58.2'
ram      = '512'

Vagrant::Config.run do |config|
  config.vm.box = box
  config.vm.box_url = url
  config.vm.host_name = hostname
  config.vm.network :hostonly, ip 

  config.vm.customize [
    'modifyvm', :id,
    '--name', hostname,
    '--memory', ram
  ]
end

Vagrant.configure("2") do |config|
  config.vm.network "forwarded_port", guest: 8080, host: 9090
end
