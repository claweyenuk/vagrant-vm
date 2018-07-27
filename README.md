# Dev VM

This is a simple VM that has a network setup that allows for easy
testing of a web server.

The network is setup so that the VM is completely accessible only
from the host at <192.168.56.10>.  Ping, ssh, using the web all
work with that address.

The host points point 8080 to the VM's port 80.  So if someone
outside the host wants to access the VM, they can visit
`http://<host_ip>:8080` in their browser and see the VM server.


## Setup

This requires Vagrant and Virtualbox.  In theory any version should work, but 
my experience has been that this is not always the case.  This has been
tested with the following:

    $ virtualenv.exe --version
    16.0.0

    $ vagrant -v
    Vagrant 2.1.2

## Usage

The commands below must be run from the directory with the `Vagrantfile`

* To create the VM, run `vagrant up`
* To access the VM, run `vagrant ssh` 

Alternatively, you can use ssh using:

    ssh -i .vagrant/machines/default/virtualbox/private_key -A vagrant@192.168.56.10

This will let you download code onto the VM.
