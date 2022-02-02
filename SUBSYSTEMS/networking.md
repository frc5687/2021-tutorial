# Networking Robots

Our robots have several types of networks that allow devices to communicate and coordinate to control the robot's behavior.

See the WPILib [Networking Introduction](https://docs.wpilib.org/en/stable/docs/networking/networking-introduction/index.html) for an overview.

## Radio

Either the [OpenMesh OM5P-AN or OpenMesh OM5P-AC wireless radio](https://docs.wpilib.org/en/stable/docs/controls-overviews/control-system-hardware.html#openmesh-om5p-an-or-om5p-ac-radio) is used as the robot radio to provide wireless communication functionality to the robot. The device can be configured as an Access Point for use during development or as a bridge for use during competitions.

## Internet Protocol (IP)

For IP addresses, the notation "TE.AM" is used in WPI documentation and competitions. This refers to splitting a four-digit team number into two digit pairs for the IP address octets.  For example, our team number is 5687 so our robot's roboRIO IP address will be 10.56.87.2.

*Q: do we assign IP addresses dynamically or statically?*

### Device IP Addresses

 - Radio = 10.56.87.1
 - roboRIO = 10.56.87.2, subnet mask 255.255.255.0
 - Default gateway = 10.56.87.4 the Field Network (at FRC competitions) runs a DHCP server with pools for each team that will hand out addresses in the range of 10.TE.AM.20 to 10.TE.AM.199 with a subnet mask of 255.255.255.0, and a default gateway of 10.TE.AM.4.
 - Driver Station = 10.56.87.5, subnet mask 255.0.0.0 to enable the DS to reach both the robot and Field Management System (FMS) Server, without additionally configuring the default gateway. If a static address is assigned and the subnet mask is set to 255.255.255.0, then the default gateway must be configured to 10.56.87.4.
 - IP Camera (if used) = 10.56.87.11, subnet 255.255.255.0
 - Other IP Devices = 10.56.87.6 through .10 or .12 through .19 (.11 if camera not present), subnet 255.255.255.0

### mDNS to Discover Devices

What is mDNS? Multicast Domain Name System (mDNS) is a system which allows for resolution of host names to IP addresses on small networks with no dedicated name (DNS) server. To resolve a host name a device sends out a multicast message to the network querying for the device. The device then responds with a multicast message containing its IP address. Devices on the network store this information in a cache so subsequent requests can be resolved from the cache without repeating the network query.

Basically, instead of having to know the IP address of every device on your network, you can communicate with them using their mDNS name (something like "ping roborio-2168.local" instead of "ping 10.21.68.2").

Driver Station, LabVIEW, and vscode are all programmed to discover your roboRIO using the mDNS protocol. This means that the roboRIO can be detected regardless of the interface or IP being used.

To use mDNS on FRC, a mDNS resolver must be installed on your development computer.

Windows
- mDNS resolver is installed with NI/FIRST software
- iTunes uses mDNS and installs a resolver if your Windows machine has iTunes.

Linux
- Most Linux distros have a mDNS resolver installed by default such as Ubuntu or Mint, if not
- Install nss-mDNS or Avahi or Zeroconf

Apple
- Apple Bonjour is a mDNS resolver and is installed in OSX by default

Most web-browsers and applications should be able to utilize the mDNS address to access the roboRIO webserver as long as an mDNS provider is installed.

For example: you should be able to navigate to http://roborio-2168.local from any browser, or application requiring a hostname (like Putty, or Filezilla).

Please note the following exceptions:

- Chrome - In Google Chrome, a trailing ‘/’ must be appended to access mDNS addresses (eg.roboRIO-2168.local/)

#### How do I set up my Robot Network to use mDNS?

USB If using the USB interface, no setup is required. The roboRIO driver will automatically configure the IP address of the host (your computer) and roboRIO and the software listed above should be able to locate and utilize your roboRIO

Ethernet/Wireless

The 2015 Bridge Configuration Utility has been modified to enable the DHCP server on the DAP1522 radio in the home use case (AP mode), if you are putting the DAP1522 in bridge mode and using a router you can enable DHCP addressing on the router. The bridge is set to the same team based IP address as before (10.TE.AM.1) and will hand out DHCP address from 10.TE.AM.20 to 10.TE.AM.199

roboRIO Ethernet Configuration

The roboRIO Ethernet interface should be set to DHCP. When connected to the DAP1522 bridge, the roboRIO will receive an IP from the bridge. When tethered directly to a PC, both devices will self-assign IPs.

PC Configuration

When connecting via Ethernet (to either the radio or directly to the roboRIO) or Wireless (to the DLink radio), your computer adapter should be set to DHCP. When connecting through the DAP1522, your PC will receive an IP address from the radio. If tethered directly to the roboRIO both devices will self-assign IPs.

mDNS works on the field such that all of your devices are located using their mDNS address so static IPs are no longer required.

#### mDNS IP Lists

IPs for system components:

- roboRIO USB: 172.22.11.2
- roboRIO mDNS: roboRIO-####.local (where #### is your team number with no leading zeroes) You should be able to use this address to communicate with the roboRIO over either interface through ping, browser, etc.
- Robot radio: 10.TE.AM.1 (where TE.AM is your 4 digit team number with leading zeroes if required) (This is the address set by the FRC Bride Configuration Tool)
- roboRIO Ethernet: DHCP, assigned by the robot radio
- Driver Station PC: DHCP, assigned by the robot radio
- Additional programming computers: DHCP, assigned by the robot radio (DHCP range: 10.TE.AM.20 to 10.TE.AM.199)

Note: You can still assign static IPs to any device on the robot. However, do so between 10.TE.AM.2 and 10.TE.AM.19 so as to not interfere with the DHCP addressing on the of the field.