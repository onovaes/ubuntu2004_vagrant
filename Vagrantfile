servers=[
    {
        :hostname => "webserver1",
        :ip => "192.168.0.21"
    },
    {
      :hostname => "webserver2",
      :ip => "192.168.0.22"
    },
    {
      :hostname => "dbserver1",
      :ip => "192.168.0.23"
    }
]

Vagrant.configure(2) do |config|
    servers.each do |machine|
        config.vm.define machine[:hostname] do |node|
            node.vm.box = "bento/ubuntu-20.04"
            node.vm.hostname = machine[:hostname]
            node.vm.network "public_network", bridge: "eno1" , ip: machine[:ip]

            node.vm.provision "shell" do |s|
              ssh_pub_key = File.readlines("#{Dir.home}/.ssh/id_rsa.pub").first.strip
              s.inline = <<-SHELL
                echo #{ssh_pub_key} >> /home/vagrant/.ssh/authorized_keys
                echo #{ssh_pub_key} >> /root/.ssh/authorized_keys
              SHELL
            end
        end
    end
end