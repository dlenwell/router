router project
==============
_____________
###Problem:#
With poor internet options in my home area.. I've opted to build something interesting. A mulitple WAN router. Principle problems I am trying to solve are redundancy (auto fail over)
and stability. Basically I want to route low priority traffic (torrent, etc) over faster but more lossy networks and high priority traffic (ssh,voip,etc) over slower but stable networks).

I want to make a script that can be configured with a few values at the top that will enable this functionality in a stock ubuntu machine. 

_____________
###Solution#

* create setup_router.sh based on script demonstrated here: https://help.ubuntu.com/community/Router
* add iptables rules for passing services to specific outbound interfaces.
    *  torrent traffic goes out wlan2
    *  ssh traffic goes out eth1
    *  web traffic goes out eth1
    *  voip / messenger services go out eth1
* setup a scirpt that makes a persistant reverse-ssh tunnel to a public cloud instance over both connections to insure i can always get back into my network.

_____________
###I could use some help#
That is right... I'm not afraid to admit it when I need colaboration. I could use some help with the rules that route the different types of traffic into specific interfaces. 

_____________
Figure A:
![ScreenShot](https://raw.githubusercontent.com/dlenwell/router/master/current_network.png)


