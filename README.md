# TryHackMe-Xpath

In this module TryHackMe teaches the student how to utilize Xpath queries within Windows Powershell to parse data from Windows Event Logs.<br>
<br>
<b> Question 1:</b><br>
1. Using Get-WinEvent and XPath, what is the query to find WLMS events with a System Time of 2020-12-15T01:09:08.940277500Z?<br>
<br>
Answer: Get-WinEvent -LogName Application -FilterXPath '*/System/Provider[@Name="WLMS"] and */System/TimeCreated[@SystemTime="2020-12-15T01:09:08.940277500Z"]'<br>
<br>
<a href="https://imgur.com/hYKPMlN"><img src="https://i.imgur.com/hYKPMlN.jpg" title="source: imgur.com" /></a><br>
<br>
<b>Question 2:</b><br>
<br>
2. Using Get-WinEvent and XPath, what is the query to find a user named Sam with an Logon Event ID of 4720?<br>
<br>
Answer: Get-WinEvent -LogName Security -FilterXPath '*/System/EventID=4720 and */EventData/Data[@Name="TargetUserName"]="Sam"'<br>
<br>
<a href="https://imgur.com/g9MgcZf"><img src="https://i.imgur.com/g9MgcZf.jpg" title="source: imgur.com" /></a><br>
<br>
<b>Question 3:</b><br>
<br>
3. Based on the previous query, how many results are returned?<br>
<br>
Answer: 2<br>
<br>
<b>Question 4:</b><br>
<br>
4. Based on the output from the question #2, what is Message?<br>
<br>
Answer:  A user account was created<br>
<br>
<b>Question 5:</b><br>
<br>
5. Still working with Sam as the user, what time was Event ID 4724 recorded? (MM/DD/YYYY H:MM:SS [AM/PM])<br>
<br>
To find the answer to this question, I did a search for the event ID that they requested, which also revealed the answer to the last question. Get-WinEvent -LogName Security -FilterXPath '*/System/EventID=4724'<br>
<br>
Answer: 12/17/2020 1:57:14 PM<br>
<br>
<a href="https://imgur.com/yaSmJDT"><img src="https://i.imgur.com/yaSmJDT.jpg" title="source: imgur.com" /></a><br>
<br>
<b>Question 6:</b><br>
<br>
6. What is the Provider Name?<br>
<br>
Answer:  Microsoft-Windows-Security-Auditing
