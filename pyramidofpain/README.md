<h2>Pyramid of Pain</h2>

<p><span style="font-size:14px">You are a level one security operations center (SOC) analyst at a financial services company. You have received an alert about a suspicious file being downloaded on an employee&#39;s computer.&nbsp;</span></p>

<p><span style="font-size:14px">You investigate this alert and discover that the employee received an email containing an attachment. The attachment was a password-protected spreadsheet file. The spreadsheet&#39;s password was provided in the email. The employee downloaded the file, then entered the password to open the file. When the employee opened the file, a malicious payload was then executed on their computer.</span></p>

<p><span style="font-size:14px">You retrieve the malicious file and create a SHA256 hash of the file. You might recall from a previous course that a <strong>hash function</strong> is an algorithm that produces a code that can&#39;t be decrypted. Hashing is a cryptographic method used to uniquely identify malware, acting as the file&#39;s unique fingerprint.&nbsp;</span></p>

<p>&nbsp;</p>

<h3><span style="font-family:'Google Sans',sans-serif"><span style="color:#000000">Has this file hash been reported as malicious? Explain why or why not.</span></span></h3>

<p><span style="font-size:14px">After conducting an extensive examination, it has come to our attention that the file hash in question has been flagged as malicious by a substantial number of reputable vendors, surpassing the count of 50. Delving deeper into our analysis, we have determined that this particular file hash corresponds to the notorious malware known as Flagpro, a malicious software frequently employed by the advanced threat actor group known as BlackTech.</span></p>

<p><span style="font-size:14px">Flagpro, as a form of malware, exhibits a wide range of sophisticated techniques that enable it to infiltrate and compromise targeted systems. Its deployment has been observed in numerous high-profile cyber attacks, often resulting in significant breaches and extensive damage to the affected entities. The utilization of this file hash by the BlackTech threat actor group serves as a strong indication of their involvement and highlights the gravity of the situation at hand.</span></p>

<p>Identify <em>three</em> <strong>indicators of compromise </strong>(<strong>IoCs</strong>) that are associated with this file hash using the tabs in the VirusTotal report. Then, enter the IoCs into their respective sections in the Pyramid of Pain template.</p>

<p>Indicators of compromise are valuable sources of information for security professionals because they are used to identify malicious activity. You can choose to identify any three of the six types of IoCs found in the Pyramid of Pain:</p>

<ul>
	<li>
	<p><strong>Hash value:</strong> Hashes convert information into a unique value that can&#39;t be decrypted. Hashes are often used as unique references to files involved in an intrusion. In this activity, you used a SHA256 hash as the artifact for this investigation. Find another hash that&#39;s used to identify this malware and enter it beside the <strong>Hash values </strong>section in the Pyramid of Pain template.&nbsp;You can use the <strong>Details</strong> tab to help you identify other hashes.</p>
	</li>
	<li>
	<p><strong>IP address</strong>: Find an IP address that this malware contacted and enter it beside the <strong>IP</strong> <strong>addresses</strong> section in the Pyramid of Pain template. You can locate IP addresses in the <strong>Relations</strong> tab under the Contacted IP addresses section or in the <strong>Behavior</strong> tab under the IP Traffic section.</p>
	</li>
	<li>
	<p><strong>Domain name:</strong> Find a domain name that this malware contacted and enter it beside the <strong>Domain names </strong>section<strong> </strong>in the Pyramid of Pain template. You can find domain name information under the Relations tab. You might encounter benign domain names. Use the <strong>Detections</strong> column to identify domain names that have been reported as malicious.</p>
	</li>
	<li>
	<p><strong>Network artifact/host artifact:</strong> Malware can create network-related or host-related artifacts on an infected system. Find a network-related or host-related artifact that this malware created and enter it beside the <strong>Network/host artifacts</strong> section in the Pyramid of Pain template. You can find this information from the sandbox reports under the <strong>Behavior </strong>tab or from the Relations tab.</p>
	</li>
	<li>
	<p><strong>Tools:</strong> Attackers can use tools to achieve their goal. Try to find out if this malware has used any tool. Then, enter it beside the <strong>Tools </strong>section in the Pyramid of Pain template.</p>
	</li>
	<li>
	<p><strong>Tactics, techniques, and procedures (TTPs):</strong> TTPs describe the behavior of an attacker. Using the sandbox reports from the Behavior tab, find the list of tactics and techniques used by this malware as identified by MITRE ATT&amp;CK&reg; and enter it beside the <strong>TTPs</strong> section in the Pyramid of Pain template.&nbsp;</p>
	</li>
</ul>
<img width="1744" alt="pyramidofpain" src="https://github.com/kirkdshelton/cybersecurity_professional/assets/10577356/f4b76fc4-6a0b-46af-ae59-009525e416d7">
