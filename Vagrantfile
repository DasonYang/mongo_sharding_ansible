Vagrant.configure(2) do |config|
  config.ssh.insert_key = false
  config.vm.boot_timeout = 300

  N = 3

  (1..N).each do |node_id|
    nid = (node_id - 1)
  # test
    config.vm.define "mongo#{nid}" do |rabbitmq|
      # https://atlas.hashicorp.com/ubuntu/
      rabbitmq.vm.hostname = "mongo#{nid}"
      rabbitmq.vm.box = "ubuntu/trusty64"
      rabbitmq.vm.network "private_network", ip: "192.168.33.#{30 + nid}"
      rabbitmq.ssh.forward_agent = true
      
      rabbitmq.vm.provider "virtualbox" do |vb|
        vb.memory = 1024
        vb.cpus = 2
      end
    end
  end

end
