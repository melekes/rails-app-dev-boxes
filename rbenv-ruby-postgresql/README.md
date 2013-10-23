# A Virtual Machine for YourProjectName development

## Requirements

* [VirtualBox](https://www.virtualbox.org)

* [Vagrant](http://vagrantup.com)
    >= 1.1.2 required

* [vagrant-berkshelf](https://github.com/riotgames/vagrant-berkshelf)

  ```
  host $ vagrant plugin install vagrant-berkshelf
  ```

* [vagrant-vbguest](https://github.com/dotless-de/vagrant-vbguest)

  ```
  host $ vagrant plugin install vagrant-vbguest
  ```

* [vagrant-omnibus](https://github.com/schisamo/vagrant-omnibus)

  ```
  host $ vagrant plugin install vagrant-omnibus
  ```

## How To Build The Virtual Machine

Building the virtual machine is this easy:

    host $ git clone
    host $ cd <project_name>-dev-box
    host $ bundle install
    host $ berks install
    host $ vagrant up

That's it.

If the base box is not present that command fetches it first. After the installation has finished, you can access the virtual machine with

    host $ vagrant ssh

## Clone the source repository

Clone the source repo (make sure you are inside the
<project_name>-dev-box folder).

```
host $ git clone
host $ vagrant ssh
host $ cd /vagrant/<project_name>
```

## Recommended Workflow

The recommended workflow is

* edit in the host computer and

* test and run application within the virtual machine.

This workflow is convenient because in the host computer you normally have your editor of choice fine-tuned, Git configured, and SSH keys in place.

## Virtual Machine Management

When done just log out with `^D` and suspend the virtual machine

    host $ vagrant suspend

then, resume to hack again

    host $ vagrant resume

Run

    host $ vagrant halt

to shutdown the virtual machine, and

    host $ vagrant up

to boot it again.

You can find out the state of a virtual machine anytime by invoking

    host $ vagrant status

Finally, to completely wipe the virtual machine from the disk **destroying all its contents**:

    host $ vagrant destroy # DANGER: all is gone

Please check the [Vagrant documentation](http://vagrantup.com/v2/docs/index.html) for more information on Vagrant.

## Expert setup

You can use NFS to sync source files. To do this:

1. [Install NFS](https://coderwall.com/p/uaohzg)
2. Uncomment lines in Vagrantfile
