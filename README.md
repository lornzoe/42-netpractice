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
- TCP/IP and IPv4
	- 
- Private IP address ranges, Link-local addresses
- Subnet masks, splitting an IPv4 address into network and host parts
- Switches and Routers
- Routing Tables