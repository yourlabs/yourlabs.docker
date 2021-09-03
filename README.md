# yourlabs.docker Ansible role

One-liner to run dockerd with a firewall:

    bigsudo yourlabs.docker install_firewall=true @host

If you don't want to install or modify the firewall run:

    bigsudo yourlabs.docker @host

Best to run after ``bigsudo yourlabs.ssh @host``.

## Extra BigSudo Commands

Install a yourlabs-docker-prune systemd timer:

```sh
bigsudo yourlabs.docker prunecron @host
```

Will run docker system prune --all --force --volumes every night at midnight.

For prune only one time, run:

```sh
bigsudo yourlabs.docker prune @host
```

## Vagrant/VirtualBox

You can work in a VM if you have vagrant:

    cd yourlabs.docker && vagrant destroy -f && vagrant up
    vagrant ssh-config > ssh && bigsudo . @default --ssh-common-args="-F ssh" -v
