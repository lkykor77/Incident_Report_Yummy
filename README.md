# Incident_Report_Yummy

# Cybersecurity Incident Report for yummyrecipesforme: Applying OS Hardening Techniques

---

scenario: 
You are tasked with analyzing the situation and determining which network protocol was affected during this incident. To start, you attempt to visit the website and you also receive the error “destination port unreachable.” To troubleshoot the issue, you load your network analyzer tool, tcpdump, and attempt to load the webpage again. To load the webpage, your browser sends a query to a DNS server via the UDP protocol to retrieve the IP address for the website's domain name; this is part of the DNS protocol. Your browser then uses this IP address as the destination IP for sending an HTTPS request to the web server to display the webpage  The analyzer shows that when you send UDP packets to the DNS server, you receive ICMP packets containing the error message: “udp port 53 unreachable.” 

Now that you have captured data packets using a network analyzer tool, it is your job to identify which network protocol and service were impacted by this incident. Then, you will need to write a follow-up report. 

As an analyst, you can inspect network traffic and network data to determine what is causing network-related issues during cybersecurity incidents. Later in this course, you will demonstrate how to manage and resolve incidents. For now, you only need to analyze the situation. 

This event, in the meantime, is being handled by security engineers after you and other analysts have reported the issue to your direct supervisor. 

Part 1: Provide a summary of the problem found in the DNS and ICMP 
traffic log.

The UDP protocol reveals that:

This is based on the results of the network analysis, which show that the ICMP echo reply returned the error message: 

The port noted in the error message is used for: 

The most likely issue is:


Part 2: Explain your analysis of the data and provide at least one cause of the incident.
Time incident occurred:

Explain how the IT team became aware of the incident:

Explain the actions taken by the IT department to investigate the incident:

Note key findings of the IT department's investigation (i.e., details related to the port affected, DNS server, etc.): 

Note a likely cause of the incident:

Step 3: Provide a summary of the problem found in the tcpdump log
After analyzing the data presented to you from the tcpdump log, identify trends in the data. Assess which protocol is producing the error message from the DNS server for the yummyrecipesforme.com website. Recall that one of the ports that is displayed repeatedly is port 53, commonly used for DNS. In your analysis:  

Include a brief summary of the tcpdump log analysis and identify which protocols were used for the network traffic.

Provide a few details about what was indicated in the log.

Interpret the issues found in the log.

Record your responses in part one of the cybersecurity incident report.  

Step 4: Explain your analysis of the data and provide one solution to implement 
Now that you’ve inspected the traffic log and identified trends in the traffic, describe why the error messages appeared on the log. Use your answer in the previous step and the scenario to identify the reason behind the ICMP error messages. The error messages indicate that there is an issue with a specific port. What do the different protocols involved in the log reveal about the incident? In your response:

State when the problem was first reported.

Provide the scenario, events, and symptoms identified when the event was first reported.

Explain the current status of the issue.  

Describe the information discovered while investigating the issue up to this point.

List the next steps in troubleshooting and resolving the issue.

Provide the suspected root cause of the problem.

Record your responses in part two of the cybersecurity incident report. 

What to Include in Your Response
Be sure to address the following items in your completed activity:   

Provide a summary of the problem found in the tcpdump log

Explain your analysis of the data and provide one possible cause of the incident

--

While working as a cybersecurity analyst that specializes in providing IT services, several customers of clients reported that they could not access the client company website  yummyrecipesforme.com, a (**fictional**) website that sells recipes and cookbooks, and saw the error "destination port unreachable". A malicious actor decided to publish the website’s best-selling recipes on their website for the public to access for free. 

The attacker executed a dictionary attack; a type of brute-force attack to gain access to the web host. Later investigations revealed they repeatedly entered several known default passwords for the administrative account until they entered the correct password. After obtaining the login credentials, the malicious actor was able to access the admin panel and change our website’s source code. Investigations reveal they embedded a JavaScript function in the website's source code that prompted visitors to download and run a file upon visiting the website. After executing the file, the victims are redirected to a fake version of our website where our recipes are now available for free.

We were made aware of the incident multiple customers emailed yummyrecipesforme’s helpdesk. These customers complained that the company’s website had prompted them to download a file to update their browsers. They claimed that, after running the file, the address of the website changed and their personal systems began running slower. When responding to this incident, the website owner attempted to log in to the web host's admin panel but was unable to due to the credentials being changed. They then reached out to the website hosting provider. I and other cybersecurity analysts were then tasked with investigating this security event.

To address the incident, I created a sandbox environment to observe the suspicious website behavior. Then I ran the network protocol analyzer, tcpdump, before visiting the website, yummyrecipesforme.com. Once the website loaded, I was prompted to download a suspicious executable file to update my browser. Investigating further, I accepted the download and executed the file. Once executed, I observed that my browser redirected me to a different URL, greatrecipesforme.com, which was designed to appear like our website, yummyrecipesforme.com. However, the recipes our company sells were posted for free on this website. 

*The resulting tcpdump logs can be found in this repository.*

A senior cybersecurity professional's later analysis confirmed that the website was compromised. The analyst found that JavaScript code had been added to the website's source code to prompt our website's visitors to download an executable file. Analysis of that file found a script that redirected our visitors’ browsers from, yummyrecipesforme.com, to greatrecipesforme.com. 

The cybersecurity team also reports that the web server was impacted by a brute-force attack. The malicious attacker was able to gain access to the admin panel using a dictionary attack because the admin password was still set to its default password. Additionally, there were no security controls or security hardening techniques in place to prevent a brute-force attack. 

My task was to document the incident in detail, including identifying the network protocols used to establish the connection between the end user and the website and recommending a security action to take to prevent future brute-force attacks from occurring to improve the organization's security posture. *This follow-up report can be found in this repository.*

---
