<p><span style="font-family:Arial,Helvetica,sans-serif"><span style="font-size:14px">You&rsquo;re part of the growing security team at a company for sneaker enthusiasts and collectors. The business is preparing to launch a mobile app that makes it easy for their customers to buy and sell shoes.&nbsp;</span></span></p>

<p><span style="font-family:Arial,Helvetica,sans-serif"><span style="font-size:14px">You are performing a threat model of the application using the PASTA framework. You will go through each of the seven stages of the framework to identify security requirements for the new sneaker company app.</span></span></p>

<h2 style="text-align:center">&nbsp;</h2>

<h2 style="text-align:center"><strong><span style="font-size:16pt"><span style="font-family:'Google Sans',sans-serif"><span style="color:#000000">PASTA Worksheet</span></span></span></strong></h2>

<p>&nbsp;</p>

<hr />
<p>&nbsp;</p>

<table border="1" cellpadding="0" cellspacing="0" dir="ltr">
	<tbody>
		<tr>
			<td><strong><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Stages</span></span></strong></td>
			<td><strong><span style="font-family:Arial,Helvetica,sans-serif"><span style="font-size:16px">Sneaker Company</span></span></strong></td>
		</tr>
		<tr>
			<td><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">I. Define business and security objectives</span></span></td>
			<td><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif"><strong>Make 2-3 notes of specific business requirements that will be analyzed.</strong><br />
			Will the app process transactions? Yes, the application will process transactions through a user profile setting.&nbsp;<br />
			<br />
			Does it do a lot of back-end processing?Yes, financial transactions.<br />
			<br />
			Are there industry regulations that need to be considered? Yes, The application needs to be in compliance with PCI-DSS since it will process online financial transactions.</span></span></td>
		</tr>
		<tr>
			<td><strong><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">II. Define the technical scope</span></span></strong></td>
			<td><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif"><strong>List of technologies used by the application:</strong><br />
			Application programming interface (API)<br />
			Public key infrastructure (PKI)<br />
			SHA-256<br />
			SQL</span></span>
			<p><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">APIs are like special messengers that help people share information with each other. They are important because they let customers, partners, and employees send data to each other. But we need to be careful and think about which APIs we use because some are safer than others. When we use a lot of different APIs, it can make it easier forthreat actors&nbsp;to try and attack and steal our information. So, we need to make sure we keep our APIs safe from these attacks.</span></span></p>
			</td>
		</tr>
		<tr>
			<td><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">III. Decompose application</span></span></td>
			<td><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif"><a href="https://docs.google.com/presentation/d/1ol7y79popTFfNHM-90ES-H-i1Lpd0YNvPShxBlXozjg/template/preview" target="_blank">Sample data flow diagram</a></span></span></td>
		</tr>
		<tr>
			<td><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">IV. Threat analysis</span></span></td>
			<td><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif"><strong>List 2 types of threats in the PASTA worksheet that are risks to the information being handled by the application.</strong><br />
			<strong>What are the internal threats? </strong><br />
			injection -&nbsp;Inserting&nbsp;malicious code or commands into the system,&nbsp;to trick it into doing things it shouldn&#39;t. This can lead to serious consequences, such as unauthorized access, data breaches, or even taking control of the entire system. Injection attacks are common for SQL databases</span></span><br />
			<br />
			<span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif"><strong>What are the external threats?</strong><br />
			Session Hijacking - Stealing important information like session cookies or using techniques to guess session IDs.&nbsp;Session hijacking is possible because the app communicates cookies between multiple layers.</span></span></td>
		</tr>
		<tr>
			<td><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">V. Vulnerability analysis</span></span></td>
			<td><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif"><strong>List 2 vulnerabilities in the PASTA worksheet that could be exploited.</strong><br />
			Lack of prepared statements &amp;&nbsp;Broken API token</span></span></td>
		</tr>
		<tr>
			<td><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">VI. Attack modeling</span></span></td>
			<td><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif"><a href="https://docs.google.com/presentation/d/1FmWLyHgmq9XQoVuMxOym2PHO8IuedCkan4moYnI-EJ0/template/preview?usp=sharing&amp;resourcekey=0-zYPY7AhPJdcClXamlAfOag" target="_blank">Sample attack tree diagram</a></span></span></td>
		</tr>
		<tr>
			<td><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif">VII. Risk analysis and impact</span></span></td>
			<td><span style="font-size:14px"><span style="font-family:Arial,Helvetica,sans-serif"><strong>List 4 security controls that you&rsquo;ve learned about that can reduce risk.</strong><br />
			Regular patching and updating, Incedent Response Procedures, PCI-DSS and&nbsp;Secure Session Management</span></span></td>
		</tr>
	</tbody>
</table>
