# Saildrone Problem-1 
Proposed solutions to Saildrone Problem 1: multi-wan networking for secure remote telemetry data transfer

Background
In 2010 my company (Minnesota GeoServices) committed to a project to connect our cone penetration testing rigs to our data storage server. Our projects were mainly wind farms in remote farm country throughout the central United States. These rigs already had complicated PLC controlled hydraulic/pneumatic systems (one with remote internet control enabled) and data acquisition computers, but to collect the field data,operators needed to download the data to USB stick and upload via email from a hotel hotspot.

Our first systems used 
- an OpenWRT-flashed Netgear N600 Netgear router (model WNDR-3800)
- StrongSwan IPSEC to create a virtual private network with our server (at a fixed IP address) 
- One radio configured as a wifi client to connect to local hotspots or a 3G phone (prior to 4G availability)
- The second radio configured to provide VPN connected wifi to operator laptop.

Over time we augmented the system including
- A USB gps (Garmin 17HVS) connected to the OpenWRT router to gather realtime gps track log data and synchronize the data acquisition computer time
- A chron job to upload the track logs and any completed data acquisition files. The data was stored to a Subversion SVN synchronized file directory and the cron job committed file changes and directory additions to the SVN repository.
- A Verizon Novatel 4G LTE Broadband Router with Voice connected to the OpenWRT router to provide more reliable 4G internet service
- VNC, RDP and XMPP messaging to the data acquisition computer 


