Setup memcache server on Ubuntu 14.04 (LTS) with SASL based on http://www.shanison.com/2014/04/29/setup-memcached-with-sasl-authentication/.

# Dependencies

   - [vagrant](http://vagrantup.com)
   - [ruby](https://www.ruby-lang.org)

# Getting Started

    $ vagrant up
    $ vagrant ssh
    > cd /vagrant
    > sudo bin/setup
    > exit
    $ bin/test

# Customization

### Simple Authentication and Security Layer (SASL)

    > USR=bam sudo -E bin/setup
    > # Set SASL password for user: bam
    > exit
    $ MEMCACHE_URL=memcache://bam:bam@10.11.12.112 bin/test

### Memory

    > # set memory in MB
    > MEM=1024 sudo -E bin/setup
    > # Set SASL password for user: bam
    > exit
    $ MEMCACHE_URL=memcache://bam:bam@10.11.12.112 bin/test

# Live

    $ ssh user@box
    > curl -fsSL https://raw.githubusercontent.com/issueapp/box-memcached/master/bin/setup | USR=bam sudo -E sh
    > sudo saslpasswd2 -a memcached -c bam
    Password:
    Again (for verification):
    > sudo chown memcache /etc/sasldb2
    > curl myipis.herokuapp.com
    55.94.13.192
    > exit
    $ MEMCACHE_URL=memcache://bam:bam@55.94.13.192 bin/test

### Troubleshoot

[add swap](https://www.digitalocean.com/community/tutorials/how-to-add-swap-on-ubuntu-14-04)
