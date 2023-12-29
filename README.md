<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>Email Configuration</h1>
I will demonstrate how to configure osTicket's email system using Gmail. This is set to enable proper email forwarding and communication between the end user and ticketing staff in charge of resolving tickets. 
<br />



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
I navigated to the Gmail account linked to the help desk organization. In the settings window I needed to enable the IMAP protocol forwarding option to retreive messages from any device. In the past, the "less secure app" option needed to be enabled. The way I went around this was to add an app password. I then inputted that password in the email settings in osTicket under the admin panel. 

![image](https://github.com/jonathansantacruz3/email-config/assets/151465848/5bbc6294-d323-44d4-abff-ef4195e923d8)


![image](https://github.com/jonathansantacruz3/email-config/assets/151465848/c64970ee-8757-4599-b412-c083157f5e11)


![image](https://github.com/jonathansantacruz3/email-config/assets/151465848/db673cd0-86d8-4e17-bf19-a690721a67df)


![image](https://github.com/jonathansantacruz3/email-config/assets/151465848/2878222f-8bf8-40a2-b9e6-b20978b364f9)



osTicket:
In this step, I headed over to the Admin Panel and under the "Email" tab, click on "Add New Email". I entered the email that will be associated with the creation of support tickets and an email name to make it easier to identify what the email address is for. 

![image](https://github.com/jonathansantacruz3/email-config/assets/151465848/502eebfe-7cf6-4b6e-ba93-69ac9cbfa18a)





In the "New Ticket Settings" section, it gives the option to assign the preferred department, priority, help topic, and auto-response attached to new tickets.

![image](https://github.com/jonathansantacruz3/email-config/assets/151465848/3d0dd463-8763-4044-843b-e51f1a6810a4)


The section below this is where the credentials for the corresponding email used by the help desk is inputted. These credentials are the same I use to log in to my Gmail inbox. 

![image](https://github.com/jonathansantacruz3/email-config/assets/151465848/71004c4b-1ca5-4e6e-a962-2e05ec2a82f7)



In the next section for fetching emails I enabled the status and entered the host name "imap.gmail.com" which is linked to Gmail and IMAP. I wanted encrypted communication so I chose the protocol SSL in the drop down menu and entered the accompanied port number "993". In a help desk environment, response can be crucial in emergency scenerios so I set the fetch frequency to every minute. The emails per fetch setup depends on the size of the company and for this demonstration I went with 20. The subsection of what to do to emails after they are fetched is up to you or the organiation. I decided to move them to a folder named "osTicket" to ensure I have them in case they are needed for reference in the future.

![image](https://github.com/jonathansantacruz3/email-config/assets/151465848/3585a602-4673-4074-816e-e5073274e6d4)



<h3>2. Routing Outgoing Emails</h3>

For this step I enabled sending email via SMTP. The host name for SMTP and Gmail is ssl://smtp.gmail.com and the port number is 465. I made sure "Authentication Required" is turned on and I saved my changes. 

![image](https://github.com/jonathansantacruz3/email-config/assets/151465848/d4b9218b-18e2-4e06-825b-f6c865d30232)


The last step to configure is while in the Admin's panel and "Settings" under the "Email" tab, I enabled "Email Fetching" in the "Incoming Emails" section. 

![image](https://github.com/jonathansantacruz3/email-config/assets/151465848/6b1166e5-1178-4e80-a0fd-f24c47fe3338)


<h3>3. Proper Email Configuration Verification</h3>

In this step I was in the Admin's panel, "Diagnostics" window under the "Emails" tab. In the "From" drop down menu I chose the email I just configured and sent the test email to my administrator email. I then logged into that admin email account and verified that I received the test email in my inbox. I then responded back to the support email for verification on the other end. Once the test email came back I also confirmed that it was moved over to the osTicket folder. 

![image](https://github.com/jonathansantacruz3/email-config/assets/151465848/d2b65015-b75e-4eff-847a-b8eac25fd66d)

![image](https://github.com/jonathansantacruz3/email-config/assets/151465848/57083893-0ffd-4992-afa5-a6d74ddb8d07)

![image](https://github.com/jonathansantacruz3/email-config/assets/151465848/26253455-3afb-4dce-ae8c-c7e1d58473d3)



This is how to properly configure an email to the osTicket system. 

Thanks for reading!


