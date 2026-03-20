*This project has been created as part of the 42 curriculum by lyanga.*

# Description
NetPractice is a practical exercise that covers basic networking concepts including IPv4 Network addresses, subnet masks, default gateways, switches, routers (routing tables), and how they interact with one another.

This project puts the evaluatee under scrutiny by pitting them against several exercises, involving configuration of small-scale networks, in a limited timeframe to demonstrate familiarity and proficiency in the topics covered.

The whole project, including evaluation, is done on a training interface, run on a browser.

# Instructions
Unlike most other 42 projects, there are no binaries or executables to compile in NetPractice.

Instead, a training interface run on a local web server is used to do the project.

The training interface has 2 modes: `Training` and `Evaluation`:

- Training mode is used with the evaulatee's intranet login to generate a specific set of 10 levels.
	- These levels are for the evaluatee to practice and generate the configuration files required for submission
- Evaluation mode generates 3 random levels from 6 to 10, and is expected to be solved in 15 minutes.

For each level, a non-functioning network diagram is presented and must be modified the until the network functions properly and achieves its required objectives.

## Running the training interface
- Download the latest net_practice.tgz file from the 42 intra project page and extract it to any folder of choice.
- In this extracted folder, run the `run.sh` file. This shell script will launch a web server and open your preferred web browser to the dedicated page. 
	- If the `run.sh` script does not function properly, the project can still be accessed manually:
	- Run `python3 -m http.server 49242` (Port number can be changed)
	- In your web browser, navigate to the URL "http://localhost:49242” (or any other port you may have chosen).

## Exporting configurations
- In each level, there is an interface at the top that lists the objectives of the levels, and buttons to verify the current configuration and to export it.
	- The `Get my config` button will export the current level's configuration into a .json file.

## Submission details
- A total of **11 files** should be present at the repository's root:
	- **README.md**: To allow anyone unfamiliar with the project to quickly understand what the project is about, how to run it, and where to find more information on the project and the topics covered.
		- Explicit requirements for the file can be found in the subject's PDF.
	- **10 exported configuration files**: Each level has its own configuration file, and needs to be placed at the repository root.
		- The assumed purpose of these configuration files is mainly for Moulinette to validate, and not intended for the evaluator to use since there's no way to specifically import configurations into training interface.

# Resources

## Networking resources covered by the project
- TCP/IP
	- TCP/IP (Internet Protocol Suite) is the framework for explaining how data is communicated between devices over a network.
	- Uses standardised protocols to ensure reliable and efficient transmission
	- TCP (Transmission Control Protocol): Protocol to ensure data arrives exactly as it was sent.
		- NetPractice simulates the TCP connection process to help understand why connections work or fail.
- IPv4
	- A 32-bit number of an IP address.
		- Divided into 4 "blocks";
		- e.g. `192.168.100.1` is represented as `11000000.10101000.01100100.00000001`
	- NetPractice only utilises IPv4 addresses and not IPv6.
- Special IP ranges
	- Certain address ranges are reserved for Private Networks:
		- 10.0.0.0 - 10.255.255.255
		- 172.16.0.0 – 172.31.255.255
		- 192.168.0.0 – 192.168.255.255
	- The following address range is reserved for so-called loopback addresses:
		- 127.0.0.0 – 127.255.255.255
	- While there are more special IP ranges (e.g. Link-local addresses, `169.254.0.0/16`), for NetPractice these are the main ones that the evaluatee has to deal with.
- Subnet masks, splitting an IPv4 address into network and host parts
	- Subnet masks determine which part of the IP is the Network ID and which part if the Host ID
		- e.g. `/24` or `255.255.255.0`
	- A higher bitmask (like `/30` vs `/24`) simply means a longer prefix, which results in a smaller host portion (fewer available IP addresses).
	- In a host portion, the first address (Network ID) and the last address (Broadcast ID) cannot be assigned to an interface.
	- In general, it's good practice to make subnets only as big as they need to be, for security reasons.
- Switches and Routers
	- Switches connect devices between the same local network
		- Devices connected to it must be on the same subnet.
	- Routers connect different networks together.
		- Requires an interface for each network it connects to, and each must be configured correctly for traffic to pass to and fro.
	- Routers are necessary for an Internet connection, while switches are only used for interconnecting devices.
- Routing Tables
	- A map stored in a router or host.
	- Each entry consists of **destination** and **next hop**. i.e. "If you want to send the packet to **destination**, send it to **next hop**.
	- The **next hop** must always be an IP address reachable within the router's own local network.
	- A default gateway (`default` or `0.0.0.0/0`) can be specified as a catch-all for destinations.

### Additional web resources
Wikipedia:
- https://en.wikipedia.org/wiki/Internet_protocol_suite
- https://en.wikipedia.org/wiki/Transmission_Control_Protocol
- https://en.wikipedia.org/wiki/Internet_Protocol
- https://en.wikipedia.org/wiki/IPv4
- https://en.wikipedia.org/wiki/Private_network
- https://en.wikipedia.org/wiki/Loopback#Virtual_loopback_interface

Cloudflare documentation:
- https://www.cloudflare.com/learning/network-layer/what-is-a-network-switch/

GeeksforGeeks:
- https://www.geeksforgeeks.org/computer-networks/differences-between-ipv4-and-ipv6/
- https://www.geeksforgeeks.org/computer-networks/routing-tables-in-computer-network/

Reddit community-sourced information:
- https://www.reddit.com/r/explainlikeimfive/comments/w2715i/eli5_how_does_a_switch_work_in_a_network/

### AI Usage
In this project, AI chatbots (Gemini) was used to help undertstand the relationship between the several topics covered by this project, as well as to help refine the README through error-checking (factual and grammatical).
