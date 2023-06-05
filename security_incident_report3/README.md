<h1><span style="font-family:Arial,Helvetica,sans-serif">Use&nbsp;</span>DNS &amp; HTTP traffic log</h1>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Review the scenario below. Then complete the step-by-step instructions.</span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">You are a cybersecurity analyst for yummyrecipesforme.com, a website that sells recipes and cookbooks. A disgruntled baker has decided to publish the website&rsquo;s best-selling recipes for the public to access for free.&nbsp;</span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">The baker executed a brute force attack to gain access to the web host. They repeatedly entered several known default passwords for the administrative account until they correctly guessed the right one. After they obtained the login credentials, they were able to access the admin panel and change the website&rsquo;s source code. They embedded a javascript function in the source code that prompted visitors to download and run a file upon visiting the website. After running the downloaded file, the customers are redirected to a fake version of the website where the seller&rsquo;s recipes are now available for free.</span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Several hours after the attack, multiple customers emailed yummyrecipesforme&rsquo;s helpdesk. They complained that the company&rsquo;s website had prompted them to download a file to update their browsers. The customers claimed that, after running the file, the address of the website changed and their personal computers began running more slowly.&nbsp;</span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">In response to this incident, the website owner tries to log in to the admin panel but is unable to, so they reach out to the website hosting provider. You and other cybersecurity analysts are tasked with investigating this security event.</span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">To address the incident, you create a sandbox environment to observe the suspicious website behavior. You run the network protocol analyzer tcpdump, then type in the URL for the website, yummyrecipesforme.com. As soon as the website loads, you are prompted to download an executable file to update your browser. You accept the download and allow the file to run. You then observe that your browser redirects you to a different URL, greatrecipesforme.com, which is designed to look like the original site. However, the recipes your company sells are now posted for free on the new website.&nbsp;&nbsp;</span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Using the DNS &amp; HTTP log file you produced with tcpdump, determine which network protocol is identified in the packet captures during the investigation.</span></span></p>

<p>&nbsp;</p>

<p><strong><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Review the DNS/HTTP traffic log</span></span></strong></p>

<p>14:18:32.192571 IP your.machine.52444 &gt; dns.google.domain: 35084+ A?<br />
yummyrecipesforme.com. (24)<br />
14:18:32.204388 IP dns.google.domain &gt; your.machine.52444: 35084 1/0/0 A<br />
203.0.113.22 (40)</p>

<p>14:18:36.786501 IP your.machine.36086 &gt; yummyrecipesforme.com.http: Flags<br />
[S], seq 2873951608, win 65495, options [mss 65495,sackOK,TS val 3302576859<br />
ecr 0,nop,wscale 7], length 0<br />
14:18:36.786517 IP yummyrecipesforme.com.http &gt; your.machine.36086: Flags<br />
[S.], seq 3984334959, ack 2873951609, win 65483, options [mss 65495,sackOK,TS<br />
val 3302576859 ecr 3302576859,nop,wscale 7], length 0<br />
14:18:36.786529 IP your.machine.36086 &gt; yummyrecipesforme.com.http: Flags<br />
[.], ack 1, win 512, options [nop,nop,TS val 3302576859 ecr 3302576859],<br />
length 0<br />
14:18:36.786589 IP your.machine.36086 &gt; yummyrecipesforme.com.http: Flags<br />
[P.], seq 1:74, ack 1, win 512, options [nop,nop,TS val 3302576859 ecr<br />
3302576859], length 73: HTTP: GET / HTTP/1.1<br />
14:18:36.786595 IP yummyrecipesforme.com.http &gt; your.machine.36086: Flags<br />
[.], ack 74, win 512, options [nop,nop,TS val 3302576859 ecr 3302576859],<br />
length 0<br />
...&lt;a lot of traffic on the port 80&gt;...</p>

<p>14:20:32.192571 IP your.machine.52444 &gt; dns.google.domain: 21899+ A?<br />
greatrecipesforme.com. (24)<br />
14:20:32.204388 IP dns.google.domain &gt; your.machine.52444: 21899 1/0/0 A<br />
192.0.2.17 (40)<br />
14:25:29.576493 IP your.machine.56378 &gt; greatrecipesforme.com.http: Flags<br />
[S], seq 1020702883, win 65495, options [mss 65495,sackOK,TS val 3302989649<br />
ecr 0,nop,wscale 7], length 0<br />
14:25:29.576510 IP greatrecipesforme.com.http &gt; your.machine.56378: Flags<br />
[S.], seq 1993648018, ack 1020702884, win 65483, options [mss 65495,sackOK,TS<br />
val 3302989649 ecr 3302989649,nop,wscale 7], length 0<br />
14:25:29.576524 IP your.machine.56378 &gt; greatrecipesforme.com.http: Flags<br />
[.], ack 1, win 512, options [nop,nop,TS val 3302989649 ecr 3302989649],<br />
length 0<br />
14:25:29.576590 IP your.machine.56378 &gt; greatrecipesforme.com.http: Flags<br />
[P.], seq 1:74, ack 1, win 512, options [nop,nop,TS val 3302989649 ecr<br />
3302989649], length 73: HTTP: GET / HTTP/1.1</p>

<p>14:25:29.576597 IP greatrecipesforme.com.http &gt; your.machine.56378: Flags<br />
[.], ack 74, win 512, options [nop,nop,TS val 3302989649 ecr 3302989649],<br />
length 0<br />
...&lt;a lot of traffic on the port 80&gt;...</p>

<p>&nbsp;</p>

<h1><span style="font-family:Arial,Helvetica,sans-serif">Security Incident Report</span></h1>

<h2><span style="font-family:Arial,Helvetica,sans-serif"><strong>Step 1: Identify the network protocol involved in the incident</strong></span></h2>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Based on the provided DNS/HTTP traffic log, the network protocol identified in the packet captures is HTTP (Hypertext Transfer Protocol). The log shows communication between &quot;your.machine&quot; (presumably the client machine) and &quot;yummyrecipesforme.com&quot; and &quot;greatrecipesforme.com&quot; web servers on port 80, which is the default port for HTTP.</span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">The log captures the TCP/IP handshake and subsequent data transfer between the client machine and the web servers. It includes the exchange of SYN (synchronization), SYN-ACK (synchronization acknowledgment), ACK (acknowledgment), and data packets for the HTTP requests and responses.</span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Therefore, the network protocol identified in the packet captures is HTTP, which is used for transmitting hypertext (web) content over the internet.</span></span></p>

<p>&nbsp;</p>

<h2><span style="font-family:Arial,Helvetica,sans-serif"><strong>Step 2: Document the Incident&nbsp;</strong></span></h2>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Summary: The incident involved conducting a thorough analysis of DNS and HTTP packet captures to determine the underlying network protocol employed in the communication between different machines.</span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Description: During the investigation, a DNS/HTTP traffic log was carefully examined, encompassing packet captures that documented the interaction between a client machine (referred to as &quot;your.machine&quot;) and two web servers: &quot;yummyrecipesforme.com&quot; and &quot;greatrecipesforme.com&quot;. The primary objective was to ascertain the specific network protocol employed in these captured packets.</span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Analysis: The DNS/HTTP traffic log revealed the presence of the Hypertext Transfer Protocol (HTTP) in the packet captures. The communication between the client machine and the web servers occurred over port 80, the standard port for handling HTTP traffic. Notably, the log exhibited the customary TCP/IP handshake process, involving SYN (synchronization), SYN-ACK (synchronization acknowledgment), and ACK (acknowledgment) packets. Furthermore, it included HTTP GET requests and the corresponding responses, indicating the exchange of web content between the client machine and the servers.</span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Conclusion: Based on an exhaustive analysis of the DNS/HTTP traffic log, it can be confidently concluded that the network protocol identified in the packet captures is HTTP. This protocol plays a pivotal role in facilitating the transmission of hypertext (web) content across the internet.</span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Recommendation: Further investigation may be warranted to collect additional data and analyze other network protocols if deemed necessary. It is advisable to maintain vigilant network monitoring to promptly detect any anomalous patterns or suspicious activities that may compromise the security and integrity of the network.</span></span></p>

<p>&nbsp;</p>

<h2><span style="font-family:Arial,Helvetica,sans-serif"><strong>Step 3:Recommend one remediation for brute force attacks</strong></span></h2>

<p>&nbsp;</p>

<p><span style="font-family:Arial,Helvetica,sans-serif"><span style="font-size:16px">One way to protect against brute force attacks is by using a special rule called an &quot;account lockout policy.&quot; This rule helps keep our accounts safe by setting a limit on how many times someone can try to log in with the wrong password. If someone tries too many times and can&#39;t get in, their account gets temporarily locked or disabled. This helps stop attackers from guessing passwords over and over again.</span></span></p>

<p><span style="font-family:Arial,Helvetica,sans-serif"><span style="font-size:16px">By using account lockout policies, we make it harder for bad guys to break into our accounts. It&#39;s important to set the rules just right, so it&#39;s not too hard for us to log in but also not too easy for the bad guys to get in. We can keep an eye on how many times people fail to log in and see if there are any suspicious activities. This way, we can make sure our accounts are safe and secure.</span></span></p>

<p>&nbsp;</p>
