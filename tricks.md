# A bunch of nice tricks

Extract pages from pdf

    gs -dBATCH -dNOPAUSE -q -sDEVICE=pdfwrite -dFirstPage=3 -dLastPage=5 -sOUTPUTFILE=input.3_5.pdf input.pdf

Disable mouse in vim
    
    :set mouse=

Check the host

    whois www.google.com
    host www.google.com

Curl

    curl -v -o /dev/null "http://www.google.com"

Spoof MAC Address

    sudo ifconfig wlan0 hw ether 5c:ac:4c:9a:00:11

SCP Usage

    http://www.hypexr.org/linux_scp_help.php

Apt-Get Package Management

    apt-cache search maven

No-op in #!/bin/sh

    :

System Performance Monitoring

    top
    
    # sudo apt-get install sysstat
    # http://www.thegeekstuff.com/2011/03/sar-examples/
    iostat -xcm 5
    pidstat 5
    vmstat 5

proc fs

    http://www.centos.org/docs/5/html/Deployment_Guide-en-US/s1-proc-topfiles.html

sorting

    # sort by second column, numeric, using tab as delimiter
    grep "SOME_TEXT" 0001.txt | sort -nk 2 -t $'\t' > output1.txt

zsh

    http://www.zzapper.co.uk/zshtips.html
    