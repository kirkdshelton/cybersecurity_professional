<p><span style="font-size:16px"><strong>Assignment: Analyze the data presented to you from the DNS and ICMP traffic log and identify trends in the data. Afterwards, create a security incident report.</strong></span></p>

<p>&nbsp;</p>

<p>13:24:32.192571 IP 192.51.100.15.52444 &gt; 203.0.113.2.domain: 35084+ A?<br />
yummyrecipesforme.com. (24)<br />
13:24:36.098564 IP 203.0.113.2 &gt; 192.51.100.15: ICMP 203.0.113.2<br />
udp port 53 unreachable length 254<br />
13:26:32.192571 IP 192.51.100.15.52444 &gt; 203.0.113.2.domain: 35084+ A?<br />
yummyrecipesforme.com. (24)<br />
13:27:15.934126 IP 203.0.113.2 &gt; 192.51.100.15: ICMP 203.0.113.2<br />
udp port 53 unreachable length 320<br />
13:28:32.192571 IP 192.51.100.15.52444 &gt; 203.0.113.2.domain: 35084+ A?<br />
yummyrecipesforme.com. (24)<br />
13:28:50.022967 IP 203.0.113.2 &gt; 192.51.100.15: ICMP 203.0.113.2<br />
udp port 53 unreachable length 150</p>

<p>&nbsp;</p>

<h1><span style="font-family:Arial,Helvetica,sans-serif">Security Incident Report</span></h1>

<p><span style="font-family:Arial,Helvetica,sans-serif"><span style="font-size:12pt"><span style="color:#000000"><strong>Part 1: Provide a summary of the problem found in the DNS and ICMP traffic log</strong></span></span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">The DNS and ICMP traffic log indicates a recurring issue with the resolution of the domain name &quot;yummyrecipesforme.com.&quot; The DNS queries from the source IP address 192.51.100.15 are sent to the destination IP address 203.0.113.2 on port 53, which is the default port for DNS traffic. However, the ICMP responses from 203.0.113.2 indicate that the destination server is unreachable on UDP port 53.&nbsp;The log shows these queries made at specific timestamps.&nbsp;The ICMP messages have varying lengths, indicating different specific issues encountered.&nbsp;This issue prevents successful resolution of the domain name and could result in users being unable to access the website or services associated with it. Further investigation and troubleshooting are required to identify the cause of the unreachable server and restore proper DNS functionality for the domain.</span></span></p>

<p><span style="font-size:12pt"><span style="font-family:'Google Sans Text',sans-serif"><span style="color:#000000"><strong>Part 2: Explain your analysis of the data and provide one solution to implement</strong></span></span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif"><span style="color:#000000">The incident was reported when s</span>everal customers contacted our company to report that they were not able to access the company website www.yummyrecipesforme.com, and saw the error &ldquo;destination port unreachable&rdquo; after waiting for the page to load.&nbsp;</span></span></p>

<p>&nbsp;</p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">The current status of the issue is that there is an ongoing problem with the resolution of the domain &quot;yummyrecipesforme.com.&quot; The DNS queries from the source IP address 192.51.100.15 to the destination IP address 203.0.113.2 on port 53 are consistently resulting in ICMP responses indicating that the destination server is unreachable on UDP port 53.</span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">It appears that the issue persists throughout the logged timeframe, as the same sequence of DNS queries and corresponding ICMP responses repeats. This suggests that the problem is not resolved and continues to impact the ability to resolve the domain name &quot;yummyrecipesforme.com.</span></span></p>

<p>&nbsp;</p>

<p><strong><span style="font-family:Arial,Helvetica,sans-serif"><span style="font-size:16px">*Based on the recurring pattern of DNS queries failing to reach the destination server and the ICMP responses indicating that the server is unreachable, the following could potentially be the root cause.</span></span></strong></p>

<ol>
	<li>
	<p><span style="font-family:Arial,Helvetica,sans-serif"><span style="font-size:16px">Network connectivity issues: There might be network connectivity problems between the source IP address (192.51.100.15) and the destination IP address (203.0.113.2). These issues could be related to network misconfigurations, firewall rules blocking the communication, or network infrastructure problems.</span></span></p>
	</li>
	<li>
	<p><span style="font-family:Arial,Helvetica,sans-serif"><span style="font-size:16px">DNS server misconfiguration: The destination DNS server (203.0.113.2) could be misconfigured, leading to its unresponsiveness on UDP port 53. This misconfiguration could be related to incorrect DNS settings, DNS server software issues, or other configuration errors.</span></span></p>
	</li>
	<li>
	<p><span style="font-family:Arial,Helvetica,sans-serif"><span style="font-size:16px">Firewall or security restrictions: Firewall rules or other security measures in place could be blocking the communication between the source and destination IPs on port 53, preventing successful DNS resolution.</span></span></p>
	</li>
	<li>
	<p><span style="font-family:Arial,Helvetica,sans-serif"><span style="font-size:16px">Server unavailability or downtime: The destination server might be experiencing temporary unavailability or downtime, resulting in the ICMP responses indicating its unreachable status.</span></span></p>
	</li>
</ol>

<p><strong><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">*To determine the actual root cause of the problem, a more thorough investigation and analysis of the network infrastructure, DNS server configuration, and potential security measures is suggested.</span></span></strong></p>

<p>&nbsp;</p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif"><strong>Implement necessary fixes:</strong> Once the root cause of the issue has been identified, implement the appropriate fixes. This may involve adjusting network configurations, updating DNS server settings, modifying firewall rules, or addressing server-related problems.</span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif"><strong>Monitor and verify resolution:</strong> After implementing the fixes, closely monitor the DNS resolution process and verify that the issue has been resolved. Continuously monitor the network for any recurring issues and ensure the DNS resolution remains stable.</span></span></p>

<p>&nbsp;</p>
