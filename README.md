# Incident_Report_Yummy

# Cybersecurity Incident Report for yummyrecipesforme: Applying OS Hardening Techniques

---

While working as a cybersecurity analyst that specializes in providing IT services, several customers of clients reported that they could not access the client company website  yummyrecipesforme.com, a (**fictional**) website that sells recipes and cookbooks, and saw the error "destination port unreachable". A malicious actor decided to publish the website’s best-selling recipes on their website for the public to access for free. 

The attacker executed a dictionary attack; a type of brute-force attack to gain access to the web host. Later investigations revealed they repeatedly entered several known default passwords for the administrative account until they entered the correct password. After obtaining the login credentials, the malicious actor was able to access the admin panel and change our website’s source code. Investigations reveal they embedded a JavaScript function in the website's source code that prompted visitors to download and run a file upon visiting the website. After executing the file, the victims are redirected to a fake version of our website where our recipes are now available for free.

We were made aware of the incident multiple customers emailed yummyrecipesforme’s helpdesk. These customers complained that the company’s website had prompted them to download a file to update their browsers. They claimed that, after running the file, the address of the website changed and their personal systems began running slower. When responding to this incident, the website owner attempted to log in to the web host's admin panel but was unable to due to the credentials being changed. They then reached out to the website hosting provider. I and other cybersecurity analysts were then tasked with investigating this security event.

To address the incident, I created a sandbox environment to observe the suspicious website behavior. Then I ran the network protocol analyzer, tcpdump, before visiting the website, yummyrecipesforme.com. Once the website loaded, I was prompted to download a suspicious executable file to update my browser. Investigating further, I accepted the download and executed the file. Once executed, I observed that my browser redirected me to a different URL, greatrecipesforme.com, which was designed to appear like our website, yummyrecipesforme.com. However, the recipes our company sells were posted for free on this website. 

*The resulting tcpdump logs can be found in this repository.*

A senior cybersecurity professional's later analysis confirmed that the website was compromised. The analyst found that JavaScript code had been added to the website's source code to prompt our website's visitors to download an executable file. Analysis of that file found a script that redirected our visitors’ browsers from, yummyrecipesforme.com, to greatrecipesforme.com. 

The cybersecurity team also reports that the web server was impacted by a brute-force attack. The malicious attacker was able to gain access to the admin panel using a dictionary attack because the admin password was still set to its default password. Additionally, there were no security controls or security hardening techniques in place to prevent a brute-force attack. 

My task was to document the incident in detail, including identifying the network protocols used to establish the connection between the end user and the website and recommending a security action to take to prevent future brute-force attacks from occurring to improve the organization's security posture. *This follow-up report can be found in this repository.*

---
