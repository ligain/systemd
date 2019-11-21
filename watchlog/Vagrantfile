# -*- mode: ruby -*-
# vim: set ft=ruby :


Vagrant.configure("2") do |config|
    config.vm.box = "centos/8"
    config.vm.box_version = "1905.1"

    config.vm.provision "shell", inline: <<-SHELL
    # Add watchlog service
    cp /vagrant/watchlog/watchlog /etc/sysconfig/
    cp /vagrant/watchlog/watchlog.sh /opt/
    chmod +x /opt/watchlog.sh
    cp /vagrant/watchlog/watchlog.service /vagrant/watchlog/watchlog.timer /etc/systemd/system/
    echo "42\nALERT" > /var/log/watchlog.log
    systemctl start watchlog.timer
    systemctl start watchlog
    systemctl -l status watchlog.timer
    sleep 2m
    tail -n 20 /var/log/messages
    SHELL
end
