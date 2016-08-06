### A local Vagrant environment for Ruby development provisioned by Ansible

> Has Node 4.4.7

> Uses Rbenv



* Install Virtual Box
* Install Vagrant
* Install Ansible 2.x
* Clone repository and run
```
$ vagrant up --provision
```

This will run the Vagrantfile, followed by the Ansible playbook.

The `apps` directory maps to `/apps/` in the guest machine.

Currently, port forwarding is set to `:3000`, so from inside the VM, if you want to run the rails server (e.g.), you would run
```
rails s -b 0.0.0.0 -p 3000
```
You'll also want to add the private network IP used by Vagrant to your `/etc/hosts` file:
```
sudo sh -c "echo 192.168.211.39 local.dev >> /etc/hosts"
```

Then, you can visit `local.dev:3000`
