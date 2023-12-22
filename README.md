<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>Email Configuration</h1>
I will demonstrate how to configure osTicket's email system using Gmail. This is set to enable proper email forwarding and communication between the end user and ticketing staff in charge of resolving tickets. 
<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Configure Emails with osTicket](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Hyper-V (Virtual Machines/Compute)
- Internet Information Services (IIS)
- osTicket Platform

<h2>Operating Systems Used </h2>

- Windows 11 Pro</b>

<h2>Required Steps for Proper Email Configuration</h2>

- Routing Incoming Emails 
- Routing Outgoing Emails 
- Proper Email Configuration Verification

<h2>Email Configuration Steps</h2>

In osTicket, multiple email accounts can be set up to administer the organization's email communication. When configured properly, the incoming email to the system will be converted to support tickets (piping) to allow centralized and manageable support requests. 

<h3>1. Routing Incoming Emails</h3>

Gmail Account:
I navigated to the Gmail account linked to the help desk organization. In the settings window I needed to turn on the option for "Less secure app access" and enable the IMAP protocol forwarding option to retreive messages from any device. 

osTicket:
In this step, I headed over to the Admin Panel and under the "Email" tab, click on "Add New Email". I entered the email that will be associated with the creation of support tickets and an email name to make it easier to identify what the email address is for. 


In the "New Ticket Settings" section, it gives the option to assign the preferred department, priority, help topic, and auto-response attached to new tickets.


The section below this is where the credentials for the corresponding email used by the help desk is inputted. These credentials are the same I use to log in to my Gmail inbox. 


In the next section for fetching emails I enabled the status and entered the host name "imap.gmail.com" which is linked to Gmail and IMAP. I wanted encrypted communication so I chose the protocol SSL in the drop down menu and entered the accompanied port number "993". In a help desk environment, response can be crucial in emergency scenerios so I set the fetch frequency to every minute. The emails per fetch setup depends on the size of the company and for this demonstration I went with 20. The subsection of what to do to emails after they are fetched is up to you or the organiation. I decided to move them to a folder named "osTicket" to ensure I have them in case they are needed for reference in the future.




<h3>2. Routing Outgoing Emails</h3>

For this step I enabled sending email via SMTP. The host name for SMTP and Gmail is smtp.gmail.com and the port number is 587. I made sure "Authentication Required" is turned on and I saved my changes. 

The last step to configure is while in the Admin's panel and "Settings" under the "Email" tab, I enabled "Email Fetching" in the "Incoming Emails" section. 



<h3>3. Proper Email Configuration Verification</h3>

In this step I was in the Admin's panel, "Diagnostics" window under the "Emails" tab. In the "From" drop down menu I chose the email I just configured and sent the test email to my administrator email. I then logged into that admin email account and verified that I received the test email in my inbox. I then responded back to the support email for verification on the other end. Once the test email came back I also confirmed that it was moved over to the osTicket folder. 


This is how to properly configure an email to the osTicket system. 

Thanks for reading!


