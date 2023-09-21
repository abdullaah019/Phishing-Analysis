<h1>Phishing Analysis</h1>

<h2>Description</h2>
The project consists of Categorizing Phishing Emails and manual Artifact Extraction.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)

<h2>Categorizing Phishing Emails:</h2>

<p> Email #1</b>
  
![image](https://github.com/abdullaah019/Phishing-Analysis/assets/139023222/e328104a-b90c-4b89-ad9a-5d5b09ce5d33)

<b>In email one, we notice that the sender is trying to get the recipient to respond to the email. It is also sent from a random email address, where the sender name does not match, and uses a different Reply-to address to receive the email response (if the recipient replies). The email is not asking us to click a link or download a file, so based on this information, it is a recon email trying to get a response from the user and begin a conversation, or it could be used simply to check if the target mailbox exists and can receive emails (although typically those emails don't bother writing anything in the email body).![image](https://github.com/abdullaah019/Phishing-Analysis/assets/139023222/92ab2831-d8ae-4d0b-9289-93e582923680)
</b> 

<p> Email #2</b>

 ![image](https://github.com/abdullaah019/Phishing-Analysis/assets/139023222/027c367f-31a5-4b63-bbbd-852b7a1e9e78)

<b>considering the context of the email, it is posing as a fraud alert for our Amazon account. However the email doesn't show any Amazon branding or styling, and the sending address is actually non-reply@email.lanhdaotaiba.com, which definitely isn't an Amazon email address. The email is using a sense of urgency to get users to click on the button without thinking properly. The email is asking us to confirm some information about ourselves to verify we own the account. Based on this information, this email is most likely to be a credential harvester, trying to extract private information from email recipients.</b> 

<p> Email #3</b>

 ![image](https://github.com/abdullaah019/Phishing-Analysis/assets/139023222/9a266178-1473-4cd8-97a8-5e60bd18caa2)

 <p> This email doesn't show any suspicious or malicious indicators and based on the information contained within the email body, this is a spam/newsletter email and is non-malicious (also known as junk mail).</b>


<p> Email #4</b>

 ![image](https://github.com/abdullaah019/Phishing-Analysis/assets/139023222/6c623a2c-60f5-466b-ad56-92f01999cefc)

 <p> This email is the subject line which creates a sense of urgency, which is often utilized by malicious emails. We also notice that this email has an attachment which we should be careful with, in case it is actually malicious. The sending address is a Gmail address, which is very suspicious considering it is claiming to be from the ‘Finance and Collection Department’ of a company. Based on the information provided, this is a malicious attachment email, where the email recipient is being convinced to open the attached docx file (which could contain malicious macros or a link to a malicious website) by claiming there will be financial consequences to the company.![image](https://github.com/abdullaah019/Phishing-Analysis/assets/139023222/41b4b9ae-4e63-405e-9ee4-dd5f139e35dd)
/b>


<h2>Manual Artifact Extraction:</h2>

Finding the sending address?
Opening the email in Sublime Text we can use the Find feature (CTRL+F) to search for “From”.
 ![image](https://github.com/abdullaah019/Phishing-Analysis/assets/139023222/0bb1311f-f16e-46fe-9cac-7019c4440815)
 
 
 
 
Finding the recipient address?
For this question we'll look for the “To” field and its value.
 
  ![image](https://github.com/abdullaah019/Phishing-Analysis/assets/139023222/3ffbfb66-dbca-4c10-9636-15c971505d19)

 
 
 
Finding is the subject line?
For this question we'll look for the “Subject” field and its value.
 
  ![image](https://github.com/abdullaah019/Phishing-Analysis/assets/139023222/65e05e7b-f0f2-4632-9180-c0eb0e5a6569)

 
 
 
What is the date and time the email was received? (Retrieve this via text editor. Format: DD MonthName YYYY XX:XX:XX)
For this question we'll look for the “Date” field and its value.
 
 ![image](https://github.com/abdullaah019/Phishing-Analysis/assets/139023222/c942b4c8-64a8-4b9a-948e-22859f39cd22)
 
 
 
 
Finding the sending server IP address?
For this question we'll search for the “X-Sender-IP” field and its value.
 
  ![image](https://github.com/abdullaah019/Phishing-Analysis/assets/139023222/ce379575-ff1b-406a-910c-dea497d8c069)

 
 
 
How to find the hostname of this IP address? (Reverse DNS Lookup)
Taking the IP from the previous question we'll open the site https://whois.domaintools.com and perform a search. We can see the resolved hostname below.
 
  ![image](https://github.com/abdullaah019/Phishing-Analysis/assets/139023222/479097fc-c3a5-4556-ab31-e6a8e10d20a9)

 
 
 
How to find full URL hyperlinked within this email?
The easiest way to retrieve this artifact is to (carefully) right-click the hyperlink when viewing the file in an email client, and select ‘Copy Hyperlink’ (or a similar option).
 
  ![image](https://github.com/abdullaah019/Phishing-Analysis/assets/139023222/7b299c65-2ac1-411d-95dc-f647f059c908)

 
 
 
How to find the root domain of the URL?
To find this we can either right-click the link in the email and select ‘copy link location’ and paste it into a program such as Notepad to see the URL text, or search for ‘http’ or ‘https’ in the email file until we find the right link. The ‘root domain’ essentially means the domain name of the URL, not including the specific resource. For this email, the URL is hxxps://www.thiswouldbeamalicioussite.com/index/2020/j411/NetflixLogin.php? (we're replaced https with hxxps to stop it from becoming hyperlinked), so the root domain is ‘thiswouldbeamalicioussite.com’.
 
    ![image](https://github.com/abdullaah019/Phishing-Analysis/assets/139023222/928b0e50-0718-4f64-bcc9-822d8f913ab2)

 
 
 
 
Finding the sending address?
Same as before, we'll use Find and search for “From”.
 
  ![image](https://github.com/abdullaah019/Phishing-Analysis/assets/139023222/adb0d1ff-2bc8-404a-a37e-dce1b682bbf6)

 
 
 
Finding the recipient address?
Searching for the “To” field and value.
 
  ![image](https://github.com/abdullaah019/Phishing-Analysis/assets/139023222/c55b1324-acaa-409f-82bc-b93127e559a5)

 
 
 
How to find the subject line?
Searching for the “Subject” field and value.
 
  ![image](https://github.com/abdullaah019/Phishing-Analysis/assets/139023222/0155131f-3bb0-4a6b-8d75-fe2db080c21a)

 
 
 
How to find the date and time the email was received? (Retrieve this via text editor. Format: DD MonthName YYYY XX:XX:XX)
Searching for the “Date” field and value.
 
 ![image](https://github.com/abdullaah019/Phishing-Analysis/assets/139023222/bfd1dd2b-167f-4e1a-a117-b5541ccde567)
 
 
 
 
How to find the sending server IP address?
Searching for the “X-Sender-IP” field and value.
 
  ![image](https://github.com/abdullaah019/Phishing-Analysis/assets/139023222/7e8bd5ae-2eb0-49aa-9c9a-ab559e1e3b97)

 
 
 
Finding the hostname of the sending server IP? (Reverse DNS Lookup)
Using the IP from the previous question, we'll submit it to https://whois.domaintools.com.
 
  ![image](https://github.com/abdullaah019/Phishing-Analysis/assets/139023222/e19c22c4-9932-48cc-a470-26f1e90e5a54)

 
 
 
Finding the full file name? (name + extension)
There are two ways we can get the file name. From within the text editor we can search for “filename”.
 
  ![image](https://github.com/abdullaah019/Phishing-Analysis/assets/139023222/2806e4a4-b1e1-42d9-a487-51bb67ae0b7d)

 
And within an email client we can see the attachment name somewhere in the interface. The location and style will vary depending on the client, but Outlook for example will show the attachment details at the top of the email. In Thunderbird, we see this at the bottom.
 
  ![image](https://github.com/abdullaah019/Phishing-Analysis/assets/139023222/ca996920-ab91-4fdd-8cfa-b114976d2b38)

 
 
 
How to find the MD5 and SHA256 hashes of the attached file? (Format: MD5 SHA256)
Open PowerShell window and use the Get-FileHash cmdlet to retrieve the MD5 and SHA256 hashes. As SHA256 is the default hashing algorithm we don't need to state it, however we must do this for MD5.
 
 
![image](https://github.com/abdullaah019/Phishing-Analysis/assets/139023222/e8566643-e3d1-46bb-b675-ac2bcc0a9509)


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
