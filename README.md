# screencasts infos 
Screencasts info
This is a fork of aberends/screencasts. 

## Hooks for specific system management

The [description in the libvirt documentation](https://libvirt.org/hooks.html#custom-event-scripts) show the power of this hook scripts. But there is not a good tutorial or example availible.

Libvir provides [filter](https://libvirt.org/formatnwfilter.html#goals) to do some static configuation, provided with any libvirt installation. But no explantion of the intention of this used filters was found. It seems the clear-filter is the standard filter loaded on any network start. But not real source for this infomation was found.

[jamilinux](https://jamielinux.com/docs/libvirt-networking-handbook/nat-based-network.html#nat-limitations) show methods for all kind of network isolated, nat and routed. The default way is explained and ways are provided to get rid of the standard rules and make your own filtering. 
Even though this seem from 2015, in 2022 this is still a good and comprehensive explanation to explore how to solve problems.

## Firewall and network filtering in libvirt
[libvirt firewall](https://libvirt.org/firewall.html) explain the tree components. If personal find this important to understand how things work. Especial the 3 types of standard configuration: isolated, nat, and routed and what they are for.

For example nat: nat: outbound traffic to the LAN is allowed, but MASQUERADED.  Hooks can be used to extend the capabilities of nat and develop custom configuration.

In this source the type=routed Allow inbound, but only to our expected subnet.So it is not like nat and limit inbound to connections. 

## iptabels done by libvirt

The intention is to write a network hook for a nat used in the libvirt environment. This is used to for kbm/qemu guest that are behind a nat network and could not be reached from outside. network hooks can be used to overcome this.

In this repo, it is only show how to make hook work, not how to overcome the base kvm/qemu guest problem. 

## A deeper explanation of the problem
A description of the problem itself is described by [Muhammad Kamran Azeem](https://cooker.wbitt.com/index.php/XEN,_KVM,_Libvirt_and_IPTables) in his article. He also explains this in a [youtube video series](https://www.youtube.com/watch?v=WXCo3KOCu8o). Both the article and the video are pretty old, but still valid, because nothing has change since.

## The  [youtube video](https://www.youtube.com/watch?v=qazma4WMFEM&t=182) show how to practice this example.
