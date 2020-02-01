
yourlabs.docker
===============

One-liner to run dockerd with a firewall:

    bigsudo yourlabs.docker @host

Best to run after ``bigsudo yourlabs.ssh @host``.

Vagrant/VirtualBox
------------------

You can work in a VM if you have vagrant:

    cd yourlabs.docker && vagrant destroy -f && vagrant up
    vagrant ssh-config > ssh && bigsudo . @default --ssh-common-args="-F ssh" -v
