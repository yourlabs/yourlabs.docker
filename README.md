# yourlabs.docker Ansible role

One-liner to run dockerd with a firewall:

    bigsudo yourlabs.docker @host

Best to run after ``bigsudo yourlabs.ssh @host``.

## Extra BigSudo Commands

Install a yourlabs-docker-prune systemd timer:

```sh
bigsudo yourlabs.docker prunecron @host
```

Will run docker system prune --all --force --volumes every night at midnight.

## Vagrant/VirtualBox

You can work in a VM if you have vagrant:

    cd yourlabs.docker && vagrant destroy -f && vagrant up
    vagrant ssh-config > ssh && bigsudo . @default --ssh-common-args="-F ssh" -v
