# A bunch of nice tricks

Extract pages from pdf

    gs -dBATCH -dNOPAUSE -q -sDEVICE=pdfwrite -dFirstPage=3 -dLastPage=5 -sOUTPUTFILE=input.3_5.pdf input.pdf

Disable mouse in vim
    
    :set mouse=

Check the hoost

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
