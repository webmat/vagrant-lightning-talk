# Vagrant lightning talk

## Getting started

	gem install vagrant
	vagrant init
	ll
	e Vagrantfile

Add following lines
		
	config.vm.box     = "precise64"
	config.vm.box_url = "http://files.vagrantup.com/precise64.box"
  config.vm.network :hostonly, "192.168.42.42"

	vagrant up
	vagrant ssh
	# or ssh vagrant@192.168.42.42

user: vagrant, pwd: vagrant (has sudo right)
user: root, pwd: vagrant

### Do crazy stuff

	sudo aptitude install htop
	htop

### Clean up the mess

	vagrant destroy && vagrant up && vagrant ssh

It's also a fully valid VirtualBox VM. (show snapshotting)

 	vagrant halt

## Why Vagrant?

- Simpler to test in clean environments
- Makes it trivial to share VMs configured perfectly
	- e.g. sharing VM with designer, with: web app, db, bg workers, search index
- Possible to create Vagrantfile with many VMs. Test simple multi-tier setups with 3-4 512Mb machines
- Supports your favorite provisioner: Chef, Puppet, Bash
- Vagrant supports plugins

	gem search -r vagrant

## More info

Vagrant runs on top of VirtualBox.

[Vagrant documentation](http://vagrantup.com)

Take 2 hours, read the doc on the site while trying stuff. You'll never go back.