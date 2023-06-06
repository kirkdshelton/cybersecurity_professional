<p><strong><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">You are a cybersecurity analyst working for a multimedia company that offers web design services, graphic design, and social media marketing solutions to small businesses. Your organization recently experienced a DDoS attack, which compromised the internal network for two hours until it was resolved.</span></span></strong></p>

<p><strong><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">During the attack, your organization&rsquo;s network services suddenly stopped responding due to an incoming flood of ICMP packets. Normal internal network traffic could not access any network resources. The incident management team responded by blocking incoming ICMP packets, stopping all non-critical network services offline, and restoring critical network services.&nbsp;</span></span></strong></p>

<p><strong><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">The company&rsquo;s cybersecurity team then investigated the security event. They found that a malicious actor had sent a flood of ICMP pings into the company&rsquo;s network through an unconfigured firewall. This vulnerability allowed the malicious attacker to overwhelm the company&rsquo;s network through a distributed denial of service (DDoS) attack.&nbsp;</span></span></strong></p>

<h1><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Incident Report Analysis&nbsp;</span></span></h1>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif"><strong>Identify:</strong>&nbsp;During a recent cyber attack on our company&#39;s network, we experienced something called a DDoS attack. This made our network stop working for a while because we received a flood of ICMP packets, which are like messages that computers use to communicate with each other. This flood of packets overwhelmed our network and caused our normal network traffic to be blocked, so our services couldn&#39;t work properly.</span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif">Protect:&nbsp;Our incident management team took quick action by blocking the incoming ICMP packets, which stopped the attack from causing further damage. They also temporarily shut down non-essential network services to focus on restoring critical ones. This helped us get back to normal after about two hours.<br />
<br />
<strong>Detect:&nbsp;</strong>After the attack, our cybersecurity team investigated what happened. They discovered that a person with malicious intent sent a large number of ICMP pings into our network through a firewall that was not properly set up. This vulnerability allowed the attacker to overload our network with a DDoS attack, disrupting our services.</span></span></p>

<p><span style="font-size:16px"><span style="font-family:Arial,Helvetica,sans-serif"><strong>Respond:</strong>&nbsp;</span>To fix this problem and make our network more secure, we took some important steps. First, we made a new rule in our firewall to control the number of ICMP packets that can come in at the same time. This helps us manage the amount of traffic and prevent our network from getting overwhelmed.</span></p>

<p><span style="font-size:16px">We also added a special check in our firewall to make sure that the IP addresses sending the ICMP packets are not fake or manipulated. This helps us verify the source of the packets and protect against attacks that try to trick us.</span></p>

<p><span style="font-size:16px">To help us detect any unusual or suspicious activity, we installed special software that monitors our network. This software keeps an eye on our traffic and looks for any patterns that could be signs of an attack. If it detects something strange, it alerts us so we can take action quickly.</span></p>

<p><span style="font-size:16px">In addition, we set up a system called IDS/IPS, which is like a security guard for our network. It checks the ICMP traffic for any signs that it might be part of an attack and filters out the suspicious packets.</span></p>

<p><span style="font-size:16px"><strong>Recover:</strong> To make sure our network stays secure, we follow the NIST Cybersecurity Framework (CSF). This helps us analyze any risks to our network and find any weak spots in our security measures. We also have rules, procedures, and training in place to protect our internal information and defend against cyber threats.</span></p>

<p><span style="font-size:16px">If we ever face another security problem, we are prepared to handle it. We have a plan to respond quickly, contain the threat, and analyze what happened so we can learn from it. Our goal is to get our network back to normal as soon as possible and make sure everything is safe and secure again.</span></p>
