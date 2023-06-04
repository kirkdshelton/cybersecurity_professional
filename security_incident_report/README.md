<h1 style="text-align:center"><span style="font-size:20pt"><span style="font-family:'Google Sans',sans-serif"><span style="color:#000000">Security Incident Report</span></span></span></h1>

<p>&nbsp;</p>

<p>&nbsp;</p>

<p><span style="font-size:12pt"><span style="font-family:'Google Sans',sans-serif"><span style="color:#000000"><strong>Section 1: Identify the network protocol involved in the incident</strong></span></span></span></p>

<p>The log entry with the code&nbsp;<strong>HTTP: GET / HTTP/1.1</strong>&nbsp;shows the browser is requesting data from&nbsp;<strong>yummyrecipesforme.com</strong>&nbsp;with the&nbsp;<strong>HTTP: GET</strong>&nbsp;method using&nbsp;<strong>HTTP</strong>&nbsp;protocol version&nbsp;<strong>1.1</strong>.&nbsp;</p>

<p>The thing that got affected during the problem is something called Hypertext transfer protocol (HTTP). To figure out what went wrong, they used a special tool called tcpdump and looked at a website called yummyrecipesforme.com. This tool helped them see what was happening with the information being sent back and forth between the website and the computers. They found out that there was a bad file being sent to people&#39;s computers using the HTTP protocol. This is a way of sending and receiving information on the internet.</p>

<p>&nbsp;</p>

<p><span style="font-size:12pt"><span style="font-family:'Google Sans',sans-serif"><span style="color:#000000"><strong>Section 2: Document the incident</strong></span></span></span></p>

<p>A change happens in the logs. The traffic is routed from the source computer to the DNS server using port&nbsp;<strong>.52444</strong>&nbsp;(<strong>your.machine.52444 &gt; dns.google.domain</strong>) to make another DNS resolution request. The DNS server routes the traffic to a new IP address (<strong>192.0.2.172)&nbsp;</strong>and its associated URL (<strong>greatrecipesforme.com.http</strong>).</p>

<p>Individuals visiting yummyrecipesforme.com were asked to download a file to update their web browsers. This file turned out to be bad and made their computers slow. A cybersecurity expert discovered that the website was manipulated by an attacker who tricked users into downloading the file. The expert found evidence in network logs showing the browser&#39;s connection to a fake website called greatrecipesforme.com. The attacker likely gained access to the website owner&#39;s account using a brute force attack. Running the malicious file caused problems on users&#39; computers.</p>

<p>In summary, when certain individuals&nbsp;went to yummyrecipesforme.com, they were tricked into downloading a harmful file disguised as a browser update. The cybersecurity expert uncovered that the website was tampered with and redirected users to a fake website. This happened because the attacker broke into the website owner&#39;s account. Running the bad file caused issues on people&#39;s computers.</p>

<p>&nbsp;</p>

<p><span style="font-size:12pt"><span style="font-family:'Google Sans',sans-serif"><span style="color:#000000"><strong>Section 3: Recommend one remediation for brute force attacks</strong></span></span></span></p>

<p>To keep the bad guys from breaking into the system, the team has a plan. They want to use something called two-factor authentication (2FA). This means that when someone tries to log in, they will need to do two things to prove it&#39;s really them.</p>

<p>First, they will enter their normal username and password. But that&#39;s not enough...&nbsp;They will also have to provide another special code called a one-time password (OTP). This code will be sent to their email or phone, and they have to type it in correctly.</p>

<p>If someone tries to break in by guessing passwords over and over again, they won&#39;t be able to get in. That&#39;s because they won&#39;t have the special code that the real user gets. So with this extra protection, the system will be much safer.</p>

<p>&nbsp;</p>

<p><br />
&nbsp;</p>

<p>&nbsp;</p>
