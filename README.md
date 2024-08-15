<h1>Splunk Investigation 4</h1>

<h2>Description</h2>
I analyzed an existing dashboard with four panels: two alert counters (Fortigate and Suricata) using '| stats count as Total', and two attack category panels using '| stats count by category | sort count desc'. The Suricata panel revealed an 'Information Leak' category with two failed 'ET WEB_SERVER WEB-PHP phpinfo access' attempts (404 status). Some Suricata logs included CVE Identifiers, while Fortigate logs had reference URLs for additional information. I created a query to count Suricata alerts by severity: 'index=* sourcetype=suricata event_type=alert "alert.severity"!="" | stats count by "alert.severity"'. This was added to the dashboard as a pie chart. I applied the same method to visualize Fortigate alerts by severity (crlevel).
<br />

<h2>Lab Certification:</h2>

<p align="center">
<br/>
<img src="https://i.imgur.com/D0VGK2b.png" height="80%" width="80%" alt="portfolio"/>
<br />


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
