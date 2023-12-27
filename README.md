# BTL1-Phishing-Capstone
BTL1 Phishing Capstone
  You have recently joined the security team at ABC Industries as a Junior SOC analyst within their security operations center (SOC). You are responsible for monitoring the SIEM platform, investigating and responding to security events, and protecting the organization from phishing attacks. You have just begun your shift, and in a new effort to proactively identify phishing emails that have made it past perimeter defenses, you have been given a number of emails that have randomly been copied from employee mailboxes. It is your job to analyze the downloaded emails, identify if any are malicious, and conduct investigations and write reports for any that are deemed to pose a risk to the organization. Reports should include a list of artifacts, analysis activities and results, and suggested defensive measures which will be reviewed by senior analysts.

A fellow analyst has already taken a look at the selection of emails and identified TWO malicious emails out of the sample of 5. Inspect the emails and write a Phishing Analysis report</h1>

<br />


<h2>Utilities Used</h2>

- <b>whois.domaintools</b>
- <b>URL2PNG</b>
- <b>Wannabrowser</b>
- <b>Virustotal</b>
- <b>Powershell</b>


<h2>Program walk-through:</h2>

<p align="center">
Step 1: Open and inspect each E-mail<br/>
<img src="https://i.imgur.com/sjC2XLS.png" height="80%" width="80%" alt="Add User"/>
<br />
  This email
<br />
<img src="https://i.imgur.com/bsW51CV.png" height="80%" width="80%" alt="Add User"/>
<br />
<img src="https://i.imgur.com/ok5tZR2.png" height="80%" width="80%" alt="Add User"/>
<br />
<img src="https://i.imgur.com/ADq1B0F.png" height="80%" width="80%" alt="Add User"/>
<br />
<img src="https://i.imgur.com/igyWlws.png" height="80%" width="80%" alt="Add User"/>
<br />
<br />
<br />
Step 2: Start a packet capture on an ethernet port and save it to a file <br/>
<img src="https://i.imgur.com/8aouJDZ.png" height="80%" width="80%" alt="Capture"/>
<br />
<img src="https://i.imgur.com/6Rg7bzM.png" height="80%" width="80%" alt="Save"/>
<br />
<br />
Step 3: Use a display filter to detect HTTPS packets<br/>
<img src="https://i.imgur.com/DOcX7YJ.png" height="80%" width="80%" alt="Display filter https/443"/>
<br />
<br /> 
Step 4: Visit a web page and detect its IP address using a display filter <br/>
<img src="https://i.imgur.com/S3Jh0by.png" height="80%" width="80%" alt="enable DHCP"/>
<br />
<br />
Step 5: Locate all HTTPS packets from a capture not containing a certain IP address<br />
<img src="https://i.imgur.com/WLrNPu9.png" height="80%" width="80%" alt="enable DHCP"/>  
<br />
</p>
