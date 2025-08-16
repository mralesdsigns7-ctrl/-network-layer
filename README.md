 network layer

 Cybersecurity Incident Report:
Network Traffic Analysis
Part 1: Provide a summary of the problem found in the DNS and ICMP traffic log.
The UDP protocol reveals that:
DNS queries sent to server 203.0.113.2 on UDP port 53 failed, returning ICMP “port unreachable” messages.
This is based on the results of the network analysis, which show that the ICMP echo reply returned the error message:
Every attempt to resolve yummyrecipesforme.com resulted in an ICMP error stating “udp port 53 unreachable.”
indicating no DNS service was listening.
The port noted in the error message is used for:
DNS (Domain Name System) resolution, which converts domain names to IP addresses.
The most likely issue is:
The DNS service at 203.0.113.2 was offline, misconfigured, or blocked by a firewall, preventing name resolution.
Part 2: Explain your analysis of the data and provide at least one cause of the incident.
Time incident occurred:
Between 13:24:32 and 13:28:50 (per tcpdump timestamps).
Explain how the IT team became aware of the incident:
Customers reported that the website was inaccessible and displayed “destination port unreachable” after delays.
Explain the actions taken by the IT department to investigate the incident:
• Verified the customer complaint by attempting to access the site.
• Used tcpdump to capture DNS and ICMP traffic.
• Analyzed packet flow, timestamps, and protocol details.
• Confirmed DNS queries failed due to UDP port 53 being unreachable.
Note key findings of the IT department’s investigation:
• All DNS requests for yummyrecipesforme.com failed.
• ICMP responses confirmed UDP port 53 was unreachable.
• Without DNS resolution, the browser could not send the HTTPS request to the web server.
Note a likely cause of the incident:
DNS server outage or firewall configuration blocking inbound DNS requests on UDP port 53
