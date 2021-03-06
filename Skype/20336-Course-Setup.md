# Core Solutions of Microsoft Lync Server 2013

## Local Lab Setup Instructions

These setup instructions are for classrooms running all the virtual machines on a single host.

1. Open `PowerShell`
1. Run the command `Enable-WindowsAudio`.
1. Open `Hyper-V Manager`.
1. Within `Hyper-V Manager` open the `Virtual Switch Manager`.
1. Select the `Adatum Data Center 2` virtual switch.
1. Change the virtual switch type to `Internal network` and click `OK`.
1. Hit the `Windows` key and open `ncpa.cpl`.
1. Open the `TCP/IPv4 Properties` for the `Adatum Data Center 1` network interface.
1. Set the following values:
   * IP address: 172.16.0.100
   * Subnet mask: 255.255.255.0
   * Default gateway: Do not set
   * Preferred DNS server: Do not set
1. Open the `TCP/IPv4 Properties` for the `Adatum Data Center 2` network interface.
1. Set the following values:
   * IP address: 172.16.1.100
   * Subnet mask: 255.255.255.0
   * Default gateway: Do not set
   * Preferred DNS server: Do not set
1. Hit the `Windows` key with `E`.
1. Right click the `D:\LON-CL1.adatum.com.RPD` file and select `Edit with Notepad++`.
1. Change line 25 to look like this: `full address:s:172.16.0.50` and save.
1. Right click the `D:\RED-CL1.adatum.com.RDP` file and select `Edit with Notepad++`.
1. Change line 25 to look like this: `full address:s:172.16.1.50` and save.
1. Reboot your computer.

## Virtual Machine Start Order

1. `LON-DC1` _Wait until it has completed booting_
1. `LON-ROUT1` _Wait until it has completed booting_
1. All `SQL` servers _Wait until they have completed booting_
1. Login to ALL the SQL servers and check the SQL services.
1. All `FE` servers.
1. `LON-CHAT1`
1. `LON-EDGE1`
1. `LON-WAC01`
1. All `CL` clients.
1. Wait until all machines are stable.
1. `LON-EX1`

Use the files on the root of `D:\` drive to remote into the client machines.




