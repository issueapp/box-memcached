This is a memcacheD with SASL setup based on http://www.shanison.com/2014/04/29/setup-memcached-with-sasl-authentication/

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
