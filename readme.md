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
