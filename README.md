# Vagrant lightning talk

## Getting started

```bash
gem install vagrant
vagrant init
ll
e Vagrantfile
```

Add following lines to Vagrantfile (and remove `config.vm.box = "base"`)


```ruby
config.vm.box     = "precise64"
config.vm.box_url = "http://files.vagrantup.com/precise64.box"
config.vm.network :hostonly, "192.168.42.42"
config.vm.share_folder "v-rails", "/u/apps/my_app", "."
```

```bash
vagrant up
vagrant ssh
# or ssh vagrant@192.168.42.42. Vagrant has tons of helpers, but there's nothing magic.
```

A properly set up Vagrant VM has

- user: vagrant, pwd: vagrant (with sudo right)
- user: root, pwd: vagrant

### Do crazy stuff

```bash
sudo aptitude install htop
htop
```

### Clean up the mess

```bash
vagrant destroy && vagrant up && vagrant ssh
```

```bash
sudo aptitude install mysql
```

It's also a fully valid VirtualBox VM. (show snapshotting in VirtualBox)

```
vagrant halt
```

## Why Vagrant?

- Simpler to test in clean environments
- Makes it trivial to share VMs configured perfectly
  - e.g. sharing VM with designer, with: web app, db, bg workers, search index
- Possible to create Vagrantfile with many VMs. Test simple multi-tier setups with 3-4 512Mb machines
- Supports your favorite provisioner: Chef, Puppet, Bash
- Vagrant has an active and growing community. Its creator just started a
  company to keep moving Vagrant forward.
- Vagrant supports plugins:

```bash
gem search -r vagrant
```

## More info

[Vagrant documentation](http://vagrantup.com)

Take 30 minutes, go through the first few articles on the doc. You'll never go back.

With an additional hour, you'll have gone through all the main doc, you'll be
able to share and update a VM with your coworkers (remember your designer who doesn't
(want to) know about installing Rails dependencies).
