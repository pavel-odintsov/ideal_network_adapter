# An Ideal Network Adapter

Here you could find requirements to ideal (not existing yet) Network adapter.

This requirements are inspired by years of development and deep work with different NIC's for processing very high amount of data.

* Fully customizable rss distribution function with abilty to do distribution based on values stored with different shifts in packet (L2TP, GRE, VXLAN friendly)
* Completely customizable by user's code offload features
* Phy inilization implemented by firmware, not by driver (driver side implementation increases complexity, just check Intel 82599).
* 32 or more hardware queues (so much nic's reduce number of threads significantly)
* Tcp, udp and ip (v6 and v4) checksumm offload for incoming and outgoing packets
* Support for line rate for interface speed operations (only 82599 chips from asic world could do line rate)
* Enough capacity of PCI-e lines, x16 or more)
* 10-40G. 10G become ordinary in servers and we need to increase port density offered by 40 ge switches)
* Batch mode operations. Ability to read packets in batches). Ability to tune timeout for buffers flush to driver. We coukd reduce pcie bus usage with this approach.
* Ability to change firmware content completely. Or ability to use multiple predefined firmwires (virtual functions could be moved to another firmwire because they are not mandatory for everyone. Same for pxe boot options).
* Timestamping support for all incoming packets. 
* Enough memory size for TX and RX buffers. Please do not try to save your money here as Intel did in XL710 cards.
* Linux, FreeBSD, DPDK, Netmap and SnabSwitch support drivers
* Open datasheets for all driver, phy and firmwire related things
* For two port nic's we should have support for hardware based briging, traffic mirroring frome one port to another.
* Nic should has option for sampling of incoming traffic. That's option very useful for network monitoring on high traffic rate
* Hardware filtering options by src ip, dst ip, ip protocol, packet lenght, packet ttl, port src and dst or even tcp packet options. That's very useful for filtering offload from os side netfilters
* Support for any SFP+ and QSFP transceivers (a lot of vendors deny "no name" modeules and enforce customers to buy their own overpriced modules)
