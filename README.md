# A vagrant config to practive provisioning with CDM

T
With these files you can setup and provision a locally running, virtual Hadoop cluster in real distributed fashion for trying out Hadoop and related technologies. It runs the latest Cloudera Hadoop distribution: **CDH5**. It also allows you to practise the use of [Cloudera Manager](http://www.cloudera.com/content/cloudera/en/products-and-services/cloudera-enterprise/cloudera-manager.html) for installing the Hadoop stack. If you're looking for a fully automated install, without user intervention, look elsewhere. I specifically made this with the goal of creating an environment ideally suited for Cloudera Manager to do its job. This gives you the freedom to actually install the services you want, and change the configuration how you see fit.


## Specs

The cluster conists of 3 nodes running ubuntu 14.04 Trusty:

* **Palpatine** - Master node with 4GB of RAM (Running the NameNode, Hue, ResourceManager etc. after installing the Hadoop services)
* **Yoda and R2D2** - 2 slaves with 2GB of RAM each (Running DataNodes)

Pro Tip you can find and change their names in the Vagrantfile.

You can uncomment the the 3-rd node in the Vagrantfile if you have enough resources

## Usage

First install [VirtualBox](https://www.virtualbox.org/) and [Vagrant](http://www.vagrantup.com/).

Install the Vagrant [Hostmanager plugin](https://github.com/smdahlen/vagrant-hostmanager)

```bash
$ vagrant plugin install vagrant-hostmanager
```

Clone this repository.

```bash
$ git clone https://github.com/DandyDev/virtual-hadoop-cluster.git
```

Provision the bare cluster. It will ask you to enter your password, so it can modify your `/etc/hosts` file for easy access in your browser. It uses the Vagrant Hostmanager plugin to do this. Also should work on windows

```bash
$ cd Dev_CDM_Practice
$ vagrant up
```

Go to the [Cloudera Manager web console](http://palpatine:7180) and follow the installation instructions. 

In the host specify the host you wish to provision on. 


