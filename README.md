#  Development Vagrant

#### Dependencies:

* [Virtualbox](https://www.virtualbox.org/)
* [Vagrant](http://www.vagrantup.com/)

---

#### What you get:

* CentOS Linux release 7.3.1611 (Core)
* Apache/2.4.6 (CentOS)
* 5.6.37 MySQL Community Server (GPL)
  * No databases, no users
* PHP 5.5.21
* Some common utils and editors

---

#### Get Started

1. Installation

```
$ git clone https://amitd@stash.cpwonlinesolutions.com:8443/scm/~amitd/vm.git
$ cd vm

# Loughborough?
$ vagrant up

# Publicly connected to the Internet?
$ NO_PROXY=1 vagrant up

# Get the IP
$ vagrant ssh
$ ifconfig | grep -A1 enp0s8 | grep inet
```

2. Add the IP to your proxy exception list.
3. Visit the IP in your browser
4. You should see a `phpinfo()` page

---

#### Synced folders
Synced folders are enabled. `src/` on the guest machine maps to `/var/www/html/` on the host machine.

---

#### PHP CLI using SCL (per terminal session)

```
$ vagrant ssh
$ scl enable php55 bash
$ php -v
```
