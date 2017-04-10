# Project 10 - Honeypot

Time spent: 3 hours spent in total

> Objective: Setup a honeypot and provide a working demonstration of its features.

### Required: Overview & Setup

- [x] A basic writeup (250-500 words) on the `README.md` desribing the overall approach, resources/tools used, findings
	Using NMap,
	nmap -Pn --script vuln 10.254.254.101
	to scan our target for vulnerabilities.
- [x] A specific, reproducible honeypot setup, ideally automated. There are several possibilities for this:
	- A Vagrantfile or Dockerfile which provisions the honeypot as a VM or container
	- A bash script that installs and configures the honeypot for a specific OS
	- Alternatively, **detailed** notes added to the `README.md` regarding the setup, requirements, features, etc.

### Required: Demonstration

- [x] A basic writeup of the attack (what offensive tools were used, what specifically was detected by the honeypot)
	nmap -Pn --script vuln 10.254.254.101->Checking all the port numbers
	<img src='http://i.imgur.com/HFY9bAO.png' title='Video Walkthrough' width='' alt='Video Walkthrough' />
- [x] An example of the data captured by the honeypot (example: IDS logs including IP, request paths, alerts triggered)
	nmap --max-parallelism 750 -Pn --script http-slowloris --script-args http-slowloris.runforever=true
	This script performs DOS Attack to the website.
	nmap -F 10.254.254.101
	This script reveals all the port the website is using.
	<img src='http://i.imgur.com/4lPFd1A.png' title='Video Walkthrough' width='' alt='Video Walkthrough' />
	sudo nmap -O 10.254.254.101
	This script detectes the os.
	<img src='http://i.imgur.com/QYtUKTa.png' title='Video Walkthrough' width='' alt='Video Walkthrough' />
- [x] A screen-cap of the attack being conducted
    
### Optional: Features
- Honeypot
	- [ ] HTTPS enabled (self-signed SSL cert)
	- [ ] A web application with both authenticated and unauthenticated footprint
	- [ ] Database back-end
	- [ ] Custom exploits (example: intentionally added SQLI vulnerabilities)
	- [ ] Custom traps (example: modified version of known vulnerability to prevent full exploitation)
	- [ ] Custom IDS alert (example: email sent when footprinting detected)
	- [ ] Custom incident response (example: IDS alert triggers added firewall rule to block an IP)
- Demonstration
	- [x] Additional attack demos/writeups
	- [ ] Captured malicious payload
	- [ ] Enhanced logging of exploit post-exploit activity (example: attacker-initiated commands captured and logged)
