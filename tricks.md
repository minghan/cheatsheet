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

Apt-Get Package Management

    apt-cache search maven

No-op in #!/bin/sh

    :
