# Description of lab topology

I use VirtualBox and Vagrant for my lab setup. My lab topology is quite simple and is based on:
https://github.com/ipspace/NetOpsWorkshop/tree/master/topologies/EOS-Leaf-and-Spine

It is leaf-spine datacenter topology running Arista vEOS with two leaf and two spine switches. I also added out-of-band management switch running Cumulus Linux and out-of-band management server.

The reason I have chosen those devices is that I am familiar with these devices as we currently use them in our production datacenter network.
