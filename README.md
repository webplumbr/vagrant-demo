# vagrant-demo
A demo using Vagrant and Ansible as the provisioner to fire up Ubuntu Trusty instance

### Requirements for the host operating system

- vagrant
- virtualbox
- ansible

I did the following on Peppermint 5 VM on VirtualBox.

``` 
sudo apt-get install vagrant virtualbox
```

After you have cloned this repository, you can add a virtual box through Vagrant which can then be used to fire up instances. The following step could take time as it downloads the desired image. In this case, Ubuntu Trusty 64-bit system.
 
``` 
vagrant box add trusty64 http://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-juju-vagrant-disk1.box
```

To list available/added boxes, you can run something like below. 

``` 
vagrant box list
```

Initialize a new box

``` 
vagrant init trusty64
```

Fire up the virtual box and run provision. The provisioner (in this case Ansible). The provisioning script (which is an ansible playbook) is meant to fire up a LAMP Server by default.

```
vagrant up --provision
```

You can ssh in to the box as follows

``` 
vagrant ssh
```

Now try accessing the demo web server as follows:

```
curl -v http://demo.local
```
 
### References

- [Vagrant documentation] (http://docs.vagrantup.com/v2/)
- [Ansible Tutorial] (https://serversforhackers.com/an-ansible-tutorial)
- [Ansible Playbook introduction] (http://docs.ansible.com/playbooks_intro.html)

