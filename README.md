# Splunk

# Vandalay Industries Monitoring Activity Instructions
# Step 1: The Need for Speed
Background: As the worldwide leader of importing and exporting, Vandalay Industries has been the target of many adversaries attempting to disrupt their online business. Recently, Vandaly has been experiencing DDOS attacks against their web servers.
Not only were web servers taken offline by a DDOS attack, but upload and download speed were also significantly impacted after the outage. Your networking team provided results of a network speed run around the time of the latest DDOS attack.

# Task: 
Create a report to determine the impact that the DDOS attack had on download and upload speed. Additionally, create an additional field to calculate the ratio of the upload speed to the download speed.
Upload the following file of the system speeds around the time of the attack.


# Speed Test File
Using the eval command, create a field called ratio that shows the ratio between the upload and download speeds.


![image](https://user-images.githubusercontent.com/80080368/122796549-86938000-d28c-11eb-9318-29de2f880f31.png)


![image](https://user-images.githubusercontent.com/80080368/122796681-aa56c600-d28c-11eb-8640-805a275d6531.png)


Create a report using the Splunk's table command to display the following fields in a statistics report:


_time
IP_ADDRESS
DOWNLOAD_MEGABITS
UPLOAD_MEGABITS
ratio


![image](https://user-images.githubusercontent.com/80080368/122796745-bfcbf000-d28c-11eb-9dd6-f8a665e1b1b0.png)




Based on the report created, what is the approximate date and time of the attack? 02/23/2020 at 2:30pm to 02/23/2020 at 8:30pm 
How long did it take your systems to recover? 6 hours

![image](https://user-images.githubusercontent.com/80080368/122797133-23eeb400-d28d-11eb-80d1-e268d6208ac1.png)



# Step 2: Are We Vulnerable?
Background: Due to the frequency of attacks, your manager needs to be sure that sensitive customer data on their servers is not vulnerable. Since Vandalay uses Nessus vulnerability scanners, you have pulled the last 24 hours of scans to see if there are any critical vulnerabilities.
For more information on Nessus, read the following link: https://www.tenable.com/products/nessus
# Task: 

Create a report determining how many critical vulnerabilities exist on the customer data server. Then, build an alert to notify your team if a critical vulnerability reappears on this server.
Upload the following file from the Nessus vulnerability scan.


Nessus Scan Results
 A report that shows the count of critical vulnerabilities from the customer database server.


![image](https://user-images.githubusercontent.com/80080368/122797325-5c8e8d80-d28d-11eb-8185-cec1cfa77413.png)

The database server IP is 10.11.36.23.
The field that identifies the level of vulnerabilities is severity.

Build an alert that monitors every day to see if this server has any critical vulnerabilities. If a vulnerability exists, have an alert emailed to soc@vandalay.com.


![image](https://user-images.githubusercontent.com/80080368/122797401-6fa15d80-d28d-11eb-9523-dc12ed0850e3.png)


![image](https://user-images.githubusercontent.com/80080368/122797519-8d6ec280-d28d-11eb-81fd-e539fb24e1e5.png)


![image](https://user-images.githubusercontent.com/80080368/122797618-a8d9cd80-d28d-11eb-9723-ab127488746c.png)


![image](https://user-images.githubusercontent.com/80080368/122797681-ba22da00-d28d-11eb-9b61-57810b05fd8a.png)




# Step 3: Drawing the (base)line
Background: A Vandaly server is also experiencing brute force attacks into their administrator account. Management would like you to set up monitoring to notify the SOC team if a brute force attack occurs again.
# Task: 
Analyze administrator logs that document a brute force attack. Then, create a baseline of the ordinary amount of administrator bad logins and determine a threshold to indicate if a brute force attack is occurring.
Upload the administrator login logs.


Admin Logins
When did the brute force attack occur? Feb 21, 2020 at 2 am.   

![image](https://user-images.githubusercontent.com/80080368/122797763-d161c780-d28d-11eb-968f-43b7a8d9b7c9.png)


Look for the name field to find failed logins. Account Name - administrator
Note the attack lasted several hours.
Determine a baseline of normal activity and a threshold that would alert if a brute force attack is occurring. Baseline for normal activity is 15 or less and a threshold for more than 18 failed login attempts. 


Design an alert to check the threshold every hour and email the SOC team at SOC@vandalay.com if triggered.



![image](https://user-images.githubusercontent.com/80080368/122798201-50570000-d28e-11eb-84f7-743c26080b08.png)

![image](https://user-images.githubusercontent.com/80080368/122798286-66fd5700-d28e-11eb-9210-f69c853697ba.png)


