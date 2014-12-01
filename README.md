# Vagrant CentOS6 PHP Development Environment

[日本語](README.ja.md)

This project sets up a CentOS 6.5 (64bit) virtual machine to run your PHP project in.  It mounts your PHP project directory so that you can use your favorite editors to work.

## Requirements

* VirtualBox - Free virtualization software [Download Virtualbox](https://www.virtualbox.org/wiki/Downloads)
* Vagrant 1.5+ - Tool for working with VirtualBox images [Download Vagrant](http://downloads.vagrantup.com/)
* Git - Version control system [Download Git](http://git-scm.com/downloads)

### Tested

* Ubuntu 14.04     - VirtualBox 4.3.18 & Vagrant 1.6.5 & Git 1.9.1
* Mac OS X 10.10.1 - VirtualBox 4.3.18 & Vagrant 1.6.5 & Git 1.9.3

## What's in the Development environment?

Some of the following are including using Chef Opscode repositories.

* PHP 5.5
  * Xdebug
  * Zend OPcache
  * APCu
* Apache 2.2
  * vhost setup for your project
* MySQL 5.1
  * **php_dev** and **php_test** databases
* phpMyAdmin 4.0
* PHPUnit 3.7
* Composer
* Git 1.7.1
* MongoDB 2.6
* Redis 2.4

(Optional)

* FuelPHP 1.x
* Phalcon 1.x / 2.x
* Beanstalkd

## Suggesting Setup & Layout

Add this vagrant-centos6-php to your project:

	$ git submodule add git@github.com:kenjis/vagrant-centos6-php.git vagrant
	$ cd vagrant
	$ vagrant up

Setup your directories something like this:

	project/
	├── public/
	└── vagrant/

## Accessing your project

* **Browser by Port Forwarding**: [http://localhost:8000](http://localhost:8000)
* **Browser by IP Address**: [http://192.168.33.33](http://192.168.33.33)
* **MySQL**: mysql:host=192.168.33.33;dbname=php_dev (root user password is set in the Vagrantfile)

### Vagrant

Here are common commands:

* `vagrant up` starts the virtual machine and provisions it
* `vagrant suspend` will save the current running state of the machine and stop it
* `vagrant halt` attempts a graceful shutdown of the machine
* `vagrant ssh` gives you SSH access to the virtual machine
* `vagrant destroy` will destroy the machine
* `vagrant status` shows status of the machine
* `vagrant global-status` shows status of all virtual machines

More in http://docs.vagrantup.com/v2/

## Thanks to

* https://github.com/iturgeon/vagrant-fuelphp