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

*This mDNS information is pulled from a description of the changes made for the 2015 season.  This info should be verified as still valid for the 2022 season.*

What is mDNS?

Multicast Domain Name System (mDNS) is a system which allows for resolution of host names to IP addresses on small networks with no dedicated name (DNS) server. To resolve a host name a device sends out a multicast message to the network querying for the device. The device then responds with a multicast message containing its IP address. Devices on the network store this information in a cache so subsequent requests can be resolved from the cache without repeating the network query.

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

USB

If using the USB interface, no setup is required. The roboRIO driver will automatically configure the IP address of the host (your computer) and roboRIO and the software listed above should be able to locate and utilize your roboRIO

Ethernet/Wireless

The 2015 Bridge Configuration Utility has been modified to enable the DHCP server on the DAP1522 radio in the home use case (AP mode). If you are putting the DAP1522 in bridge mode and using a router you can enable DHCP addressing on the router. The bridge is set to the same team based IP address as before (10.TE.AM.1) and will hand out DHCP address from 10.TE.AM.20 to 10.TE.AM.199.

roboRIO Ethernet Configuration

The roboRIO Ethernet interface should be set to DHCP. When connected to the DAP1522 bridge, the roboRIO will receive an IP from the bridge. When tethered directly to a PC, both devices will self-assign IPs.

PC Configuration

When connecting via Ethernet (to either the radio or directly to the roboRIO) or WiFi (to the radio), your computer adapter should be set to DHCP. When connecting via WiFi, your PC will receive an IP address from the radio. If tethered directly to the roboRIO both devices will self-assign IPs.

mDNS works on the field such that all of your devices are located using their mDNS address so static IPs are no longer required.

#### mDNS IP Lists

IPs for system components:

- roboRIO USB: 172.22.11.2
- roboRIO mDNS: roboRIO-####.local (where #### is your team number with no leading zeroes) You should be able to use this address to communicate with the roboRIO over either interface through ping, browser, etc.
- Robot radio: 10.TE.AM.1 (where TE.AM is your 4 digit team number with leading zeroes if required) (This is the address set by the FRC Bride Configuration Tool)
- roboRIO Ethernet: DHCP, assigned by the robot radio
- Driver Station PC: DHCP, assigned by the robot radio
- Additional programming computers: DHCP, assigned by the robot radio (DHCP range: 10.TE.AM.20 to 10.TE.AM.199)

Note: You can still assign static IPs to any device on the robot. However, do so between 10.TE.AM.2 and 10.TE.AM.19 so as to not interfere with the DHCP addressing on the field.

## Controller Area Network (CAN)

For background, see [FIRST CAN Networking](https://www.playingwithfusion.com/docview.php?docid=1206) and [Using CAN Devices](https://docs.wpilib.org/en/stable/docs/software/can-devices/using-can-devices.html).

Controller Area Networks (CAN) are commonly used in vehicles, as well as for industrial controls.

Electrically, the FRC CAN network is a two-wire bus, designed to allow dozens of devices -- known as "nodes" -- to communicate over a single network backbone. The voltage difference between the "HIGH" and "LOW" lines determines zeros and ones.  The network lets only one device speak at a time.  Message priority and collision detection are built into the physical protocol.

Specifications
 - Communication mode: bidirectional
 - Operating speed: 1 Mbps
 - Maximum bus wiring length: 40 meters
 - Messages per robot control loop: 80
 - Terminating impedance: a pair of 120-ohm resistors, one installed at each end of the bus
 - Network topologies: daisy chain or star

CAN Addresses

Every device of a given model group requires a unique CAN device ID for typical FRC use (settings, control and status). The device ID is usually expressed as a number between 0 and 62, allowing use for up to 63 Talon SRXs, 63 Victors, 63 PDPs, etc. at once. This range does not intercept with device IDs of other CAN device types. For example, there is no harm in having a Pneumatics Control Module (PCM) and a Talon SRX both with device ID 0. However, having two Talon SRXs with device ID 0 will be problematic.

 Notes
 - Never have more than 2 terminators in your CAN.
 - The roboRIO and PDP both have built-in terminating resistors to meet the terminating impedance requirement.
 - The PDP resistor may be disabled by removing a jumper.
 - The roboRIO's resistor can't be disabled, as it is meant to act as one end of the CAN bus.
 - If you have a node mounted at the end of a long arm, disable the PDP terminating resistor and install your own resistor at the extreme end of your CAN.
 - Daisy chain topology:
   - Good for electrical noise by creating a long network with close to zero-length CAN nodes.
   - Bus termination is trivial.
   - Relatively messy CAN wiring.
   - Single point of failure.
 - Star topology:
   - Difficult to terminate properly.
   - Could cause reliability issues.
   - A short-drop architecture, allowed by the CAN standard, built off of a typical daisy chain network.
   - Use a 4-drop STAR distribution board and a CANterm terminating resistor.
 - Much more data can be sent over a CAN connection than over a PWM connection - thus, CAN motor controllers are capable of a much more expansive feature-set than are PWM motor controllers.
 - CAN is bi-directional, so CAN motor controllers can send data back to the RIO, again facilitating a more expansive feature-set than can be offered by PWM Controllers.
 - CAN devices generally have their own WPILib classes.
 - The roboRIO provides a universal CAN heartbeat that any device on the bus can listen and react to. This heartbeat is sent every 20ms.

 ### CAN Hardware Devices

  - Pneumatics Control Module (PCM)
  - Pneumatic Hub (PH)
  - Power Distribution Panel (PDP)
  - Power Distribution Hub (PDH)
  - Motor controllers
    - Cross-the-Road Electronics (CTRE) Talon FX, Talon SRX, and Victor SPX
    - REV Robotics SPARK MAX
    - Playing With Fusion (PWF) Venom
  - Inertial Measurement Units (IMU)
    - CTRE Pigeon IMU

#### CANivore (CTRE)

The [CANivore](https://store.ctr-electronics.com/canivore/) is a USB-to-[CAN FD](https://store.ctr-electronics.com/can-fd/) device that allows us to add additional CAN FD busses to the roboRIO and control supported CTR Electronics devices.

### CAN-FD (CTRE)

CAN FD is the next iteration of the CAN bus data link layer. The FD stand for Flexible Data-Rate, meaning that portions of the frame is transmitted at higher data rates (up to 10Mbps). This means less bus time for more data. Additionally, a single frame can now hold up to 64 data bytes.

Current testing with the 2022 release firmware (CANivore and supported devices) has shown that a typical bus at 80% (as reported by the driver station) will be 35% when used with a CANivore (as reported by Phoenix Tuner). That’s an effective gain of 2.3X.

Currently the following products support CANFD, and therefore can be used with the CANivore

- Falcon 500 Powered by Talon FX
- CANcoder
- Pigeon 2.0 (New for 2022 Season)
- CANdle (New for 2022 Season)

Since CAN FD is an extension of CAN 2.0, the wiring requirements are similar.

- CAN bus must still have 120Ω of termination at each extreme end.
- CAN bus stub lengths must be short (typical maximum of one foot).
- Daisy chaining still recommended as this reduces stub length to near zero.

### Socket CAN

SocketCAN is a commonly used set of drivers and networking stack that allows for sending/receiving CAN frames in Linux.

## Pulse Width Modulation (PWM)

For background, see [PWM Motor Controllers in Depth](https://docs.wpilib.org/en/stable/docs/software/hardware-apis/motors/pwm-controllers.html).

PWM is a general technique for sending information or varifying the output of a motor by modulating an electrical signal.  In FRC this technique is an alternative to CAN for controlling motor speed.

## NetworkTables

[NetworkTables](https://docs.wpilib.org/en/stable/docs/software/networktables/networktables-intro.html) is a way to communicate key / value pairs between programs.

Named values are created either on the robot, driver station, or potentially an attached coprocessor, and the values are automatically distributed to all the other participants. For example, a driver station laptop might receive camera images over the network, perform some vision processing algorithm, and come up with some values to send back to the robot.

Data types for NetworkTables are either boolean, numeric, or string. Numeric values are written as double precision values. In addition you can have arrays of any of those types to ensure that multiple data items are delivered consistently. There is also the option of storing raw data which can be used for representing structured data.

Some recommendations for performance from Chief Delphi:

While the default periodic flush rate is fairly slow (10 Hz) and asynchronous, NetworkTables has very consistent low latency (e.g. 1us range) if you flush (NetworkTableInstance.getDefault().flush()) immediately after updating the values you’re sending. This is the approach used by Limelight and PhotonVision and it works very well.

Pro tip: you’ll get much better graphs if you flush NetworkTables every periodic loop (add NetworkTableInstance::GetDefault().Flush(); at the end of RobotPeriodic).

Call NetworkTableInstance.flush() from your main loop to flush the data synchronously with your updates to it. You can send data at a rate up to every 10 ms.

As Peter said, you can do NetworkTableInstance.getDefault().flush() every loop to update your values faster than the default 10hz.

We did a UDP scheme between a coprocessor and the roboRIO back in 2017. Data communication worked well, and was quite robust.

Peter's got the right answer though for 2022 - NT has the right stuff built in to do inter-processor communication. 