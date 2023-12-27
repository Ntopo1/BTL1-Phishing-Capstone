<h1># BTL1-Phishing-Capstone</h1>
<h2>Description</h2>
  You have recently joined the security team at ABC Industries as a Junior SOC analyst within their security operations center (SOC). You are responsible for monitoring the SIEM platform, investigating and responding to security events, and protecting the organization from phishing attacks. You have just begun your shift, and in a new effort to proactively identify phishing emails that have made it past perimeter defenses, you have been given a number of emails that have randomly been copied from employee mailboxes. It is your job to analyze the downloaded emails, identify if any are malicious, and conduct investigations and write reports for any that are deemed to pose a risk to the organization. Reports should include a list of artifacts, analysis activities and results, and suggested defensive measures which will be reviewed by senior analysts.
<br />
<br />
A fellow analyst has already taken a look at the selection of emails and identified TWO malicious emails out of the sample of 5. Inspect the emails and write a Phishing Analysis report.
<br />
<h2>Utilities Used</h2>

- <b>whois.domaintools</b>
- <b>URL2PNG</b>
- <b>Wannabrowser</b>
- <b>VirusTotal</b>
- <b>Powershell</b>


<h2>Program walk-through:</h2>


Step 1: Open and inspect each E-mail<br/>
<p align="center">
<img src="https://i.imgur.com/sjC2XLS.png" height="80%" width="80%" alt="Add User"/>
</p><br />
<align="left">This e-mail immediately looks suspicious.  The sending address is set as auto-confirm.info-amazon.co.uk, not amazon.co.uk. I can see it’s actually coming from QPE77756@mun.ca. The format and styling don't look like an e-mail from Amazon. The e-mail is also generically addressed to "Amazon user." This e-mail also has a call-to-action button, trying to get the user to click on the link for the "Help Page - Refund Form." This e-mail is the first Phishing e-mail.
<br />
  <p align="center">
<img src="https://i.imgur.com/bsW51CV.png" height="80%" width="80%" alt="Add User"/>
</p><br />
This e-mail also looks suspicious. Free money, who wouldn't want some? The e-mail is not addressed to anyone, suggesting it's mass-mailed. The URL is not hyperlinked, so it doesn't appear to have the user try and click on anything. thescottishsun[.]co[.]uk is a legitimate news site, and it does not appear malicious. The e-mail is a spam/scam e-mail and could be considered malicious if a person sent their personal information. But this is not the second e-mail.
<br />
  
<p align="center">
<img src="https://i.imgur.com/ok5tZR2.png" height="80%" width="80%" alt="Add User"/>
</p><br />
This is the second malicious email. The sender has a suspicious e-mail address. It is addressed generically, to "Sir/Madam." It has a call-to-action to open an attached file and it tries to create a sense of urgency if we don't act soon. The attachment is named "MALICIOUS ATTACHMENT REMOVED - SBT.txt."
<br />
<p align="center">
<img src="https://i.imgur.com/ADq1B0F.png" height="80%" width="80%" alt="Add User"/>
</p><br />
This would be classifed as spam/newsletter. The email is not using a real call-to-action even though it contains several hyperlinks. I wouldn't recommend clicking any of the links.
<br />
<p align="center">
<img src="https://i.imgur.com/igyWlws.png" height="80%" width="80%" alt="Add User"/>
</p><br />
This is another spam email trying to convince people to sign up and begin trading cryptocurrencies, and is not inherently malicious. I wouldn't recommend clicking any of the links.
<br />
<br />
<h3>Part 2: Analyze the first malicious e-mail</h3>
Step 1: Analyze the e-mail header artifacts
<br/>
<p align="center">
<img src="https://i.imgur.com/wfb82da.png" height="80%" width="80%" alt="Capture"/>
</p><br />
I open the email in a text editor to retrieve the sender's e-mail address, the date and time the e-mail is sent, the sending server's IP, the recipient and the subject line.
<br />
<br />
Step 2: Perform reverse DNS of the sender's server IP
<br /> 
<p align="center">
<img src="https://i.imgur.com/7KAdx5t.png" height="80%" width="80%" alt="Save"/>
</p>
<br />
Step 3: Copy the link and open in in a secure locations<br/>
<p align="center">
<img src="https://i.imgur.com/6tMcHdx.png" height="80%" width="80%" alt="Display filter https/443"/>
</p><br />
<p align="center">
<img src="https://i.imgur.com/ikFmD48.png" height="80%" width="80%" alt="Display filter https/443"/>
</p><br />
<br /> 
Step 4: Check the link on VirusTotal <br/>
<p align="center">
<img src="https://i.imgur.com/6YClKfc.png" height="80%" width="80%" alt="enable DHCP"/>
</p>
<br />
Step 5: Write a Phishing Analysis report for malicious e-mail 1<br />
Sender's e-mail address: auto-confirm.info-amazon.co.uk <QPE77756@mun.ca><br />
Date and time sent: 4/19/2017, 12:35 PM<br />
Sending Server IP: 68.114.190.29<br />
Reverse DNS of Sending server IP:mtaout004-public.msg.strl.va.charter.net <br />
Recipient(s):jack.tractive@abcindustries.co.uk<br />
Subject Line: Your Amazon.co.uk order of "ION Audio Turntable.."<br />
URLs: hxxp://id820update.refundsys59.co.uk/invoice103amz/index.php?ema=il=3Djack.tractive@abcindustries.co.uk<br />
<br />
This e-mail impersonates Amazon.co.uk. It asks the recipient if they have recently purchased an item. If you did not order the item it asks you to log into your account to receive a refund. It is poorly formatted.<br />
<br />Artifact Analysis:<br />
url2png: was unable to retrieve the website<br />
wannabrowser: unable to retrieve the website<br />
A VirusTotal search shows 1 security vendor flagged this URL as malicious and it was classified as malware.<br />
<br />
Suggested Defensive Measures:<br />
The web page was most likely a credential harvester before being taken down. The age of the email origin server(RegDate: 2002-03-04) does not suggest that the domain was created with malicious intent. Requesting an email gateway block for the sending address "QPE77756@mun.ca".<br />

The domain has been recognized as malicious, and there is no business justification for any employees needing to access this site. As it has a malicious reputation on VirusTotal, the entire domain can be blocked on the web proxy, preventing employees from connecting to the site. This will also make future phishing attacks using this same domain ineffective.<br />

Requesting a web proxy block for the domain "hxxp://id820update.refundsys59.co.uk/invoice103amz/index.php?ema=il=3Djack.tractive@abcindustries[.]co.uk".
<br />
<h3>Part 3: Analyze the second malicious e-mail</h3>
Step 1: Analyze the Email Header Artifacts
<br/>
<p align="center">
<img src="https://i.imgur.com/dZiIyes.png" height="80%" width="80%" alt="Capture"/>
</p><br />
I open the email in a text editor to retrieve the sender's e-mail address, the date and time the e-mail is sent, the sending server's IP, the recipient and the subject line.
<br />
<br />
Step 2: Perform reverse DNS of the sender's server IP
<br /> 
<p align="center">
<img src="https://i.imgur.com/Zi5yT2I.png" height="80%" width="80%" alt="Save"/>
</p>
<br />
Step 3: Get a hash of the malicious file<br/>
<p align="center">
<img src="https://i.imgur.com/CTUrTSQ.png" height="80%" width="80%" alt="Display filter https/443"/>
</p><br /> In this case a file hash was provided.
<br />
<p align="center">
<img src="https://i.imgur.com/xUbnK8T.png" height="80%" width="80%" alt="Display filter https/443"/>
</p>
<br /> 
Step 4: Check the file hash on VirusTotal <br/>
<p align="center">
<img src="https://i.imgur.com/mU9Z0TV.png" height="80%" width="80%" alt="enable DHCP"/>
</p><br /> 
Step 5: Write a Phishing Analysis report for malicious e-mail 2<br />
Sender's e-mail address: skly asdam <FSDFAS2423N23K@gmail[.]com><br />
Date and time sent: 6/12/2020, 8:23 PM<br />
Sending Server IP:209.85.160.173<br />
Reverse DNS of Sending server IP: mail-qt1-f173.google.com <br />
Recipient(s): matthew.beaman@abcindustries.co.uk<br />
Subject Line: COVID19 - GET TESTED NOW!<br />
Files:COVID19-Testing-Kit-2020.pdf.exe<br />
SHA256 file Hash:8b2e701e91101955c73865589a4c72999aeabc11043f712e05fdb1c17c4ab19a<br />
This e-mail attempts to impersonate the National Healthcare System or NHS. The sender intended to create a sense of urgency to claim free covid tests by having the recipient click on a malicious attached file.
<br />
Artifact Analysis: <br />
A VirusTotal search shows 59 security vendors and 1 sandbox flagged this file as malicious. Popular threat labels are trojan.zbot/foreign. This file contains a trojan or spyware.
 <br />
Suggested Defensive Measures:<br />
As the sender is using a Gmail address, the most appropriate action would be to block this specific mailbox to prevent any more incoming malicious emails from this sender.

Requesting an email gateway block for the sending address "FSDFAS2423N23K@gmail[.]com"
<br />
</p>
