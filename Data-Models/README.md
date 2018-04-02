# EOS Vlan service deployment in BGP EVPN data center fabric

Collection of playbooks that deploys a Vlan service on Arista EOS data center switches.

Initially there are two data models - first is describing services (services.yml) and second one is describing infrastructure (fabric.yml). Create-data-model.yml playbook is used to transform services-oriented data models to node-oriented model.

Create-evpn-vlan.yml playbook is used to generate EOS switch configuration from services data model. 

## Data model description

The _infrastructure_ data model in fabric.yml has these sections
- __nodes__ - a list of nodes in the network. Every node has name, mgmt IP address (used to access the node) and two loopback IP addresses - Loopback0 used in router-id and Loopback100 used as source address in Vxlan interface.
- __asn__ - a dictionary of AS numbers. Each ASN has a members list consisting of device names belonging to the AS
- __fabric__ - list of data center fabric links. Every link has left and right nodes, left_ip and right_ip IP addresses and left_port and right_port interfaces.
- __evpn__ - list of BGP evpn links used in DC fabric. EBGP is configured on evpn links.

The _services_ data model is a dictionary of vlan services with every vlan having these elements:
- __id__ - Vlan id
- __name__ - name used to describe the vlan service
