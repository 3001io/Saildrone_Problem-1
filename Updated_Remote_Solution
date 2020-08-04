Proposed Updated Remote Multi-WAN  with Satellite option

The following builds on the working remote telemetry system I had in operation for several years.

MultiWAN Component
- Server side opensource router with fixed ip address running StrongSWAN (or OpenSWAN) IPSEC and private/public key IKEV2 encryption to accept connections from wifi connection or 4G/5G LTE modem
- Redundant wifi interfaces on the embedded system computer. Many ARM based embedded linux computers have integrated wifi. These small devices draw little power compared to instrumentation systems allowing multiple wifi connections (and satellite connections as described below).
- Either USB or ethernet connection to 4G LTE broadband router or device. Options for this are constantly evolving but should have multiple radios (world capable)
- A multiwan failover to switch from wifi connection to 4G/5G depending on realibility and/or signal strength. The OpenWRT MWAN3 project has opensource code that can be purposed to this https://openwrt.org/docs/guide-user/network/wan/multiwan/mwan3 There are also linux-based devices which are modular and combine either wifi, cellular or LORAWAN radio (which could be used for satellite, see below) such as the Multitech Conduit https://www.multitech.com/brands/multiconnect-conduit or Tektelic (https://tektelic.com/wp-content/uploads/Kona-Macro.pdf). I've been using the Multitech Conduit as a LoraWAN gateway for the last two years. These are available as an IP67 model with choices of backhaul. https://www.multitech.com/brands/multiconnect-conduit-ip67
- Data could be retrieved in numerous ways but presumably is primarily time-series data (excluding pictures and sonar data). I've been using MQTT messaging to transmit data packets, which works very well and allows many options for data transfer beyond a continuous IPSEC connection. Files can also be included in mqtt messages. Ive been using the VerneMQ broker for the last 18 months to forward mqtt (https://vernemq.com/). But another option to look at is git/svn commits of a file or directory structure. Another option for data transfer is OpenNMS (Open Network Monitoring System) and OpenNMS minions (www.opennms.com). I've been a proponent of this for time-series data collection for over five years. There are collection methods for http data, mqtt messages, collectd, etc., and excellent integration with Grafana for graphing
- I've included example scripts, diagrams, presentations and other materials within this git repository.

Satellite Component

I'm less familiar with satellite telemetry, but obviously the bandwidth requirements are greatly reduced, it is more expensive, but it is also the primary method these remote systems will need to use to communicate real time data. As I mentioned above, I have been using LoraWAN radio sensors and gateways for two years now and that is the option I will focus on.

LoraWAN Solution
- Line-of-sight spread spectrum radios in the 833 (Europe), 915 (Australia/Americas), and 923mhz unlicensed bandwidth
- Low power, very long range, very low bandwidth radio solution for IOT devices
- Bandwidth is dependent on signal strength, but rule of thumb is up to 1024bps per radio. Due to the very low power requirements, multiple radios could potentially be used to transmit more data, but 1024bps should allow sufficient bandwidth to upload up to 50MB/day
- Could also be used relay data uplink between saildrones and a support ship in the 5-20 mile vicinity (similar to marine VHF radio distance)
- Available as separate devices (such as the Multitech XDot or MDots https://www.multitech.com/brands/multiconnect-xdot https://www.multitech.com/brands/multiconnect-mdot), as serial transceivers (https://tektelic.com/wp-content/uploads/Industrial-Transceiver.pdf) and as add-ons to embedded computers such as the PocketBeagle or RasPI (https://www.mikroe.com/click/wireless-connectivity/lora, https://learn.adafruit.com/lora-and-lorawan-radio-for-raspberry-pi)
- A new venture is creating a global LoraWAN service with a new satellite network (https://lacuna.space/about/). They just launched their first set of five satellites in 2019.

Please find the example scripts, diagrams and other materials in this git repository as an example of my work in this area.
