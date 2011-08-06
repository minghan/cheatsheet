# Stuff about OpenAFS and Andrew

Install OpenAFS on Debian:

    $ sudo apt-get install ssh-krb5 
    $ sudo apt-get install krb5-user
    $ sudo apt-get install openafs-client openafs-krb5

Download ``/etc/krb5.conf`` from ANDREW into LOCAL ``/etc/krb5.conf``

Starting the OpenAFS service and having fun:

    $ kinit hbovik@ANDREW.CMU.EDU

    $ sudo /etc/init.d/openafs-client start

    $ cd /afs/
    $ ls

