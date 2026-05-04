# Walkthrough

## This are the details:

Description

- Learn how to use SOC Simulator by completing your first scenario. Close all True Positive alerts to pass!
  
Scenario objectives

- Monitor and analyze real-time alerts.
- Identify and document critical events such as suspicious emails and attachments.
- Create detailed case reports based on your observations to help your team understand the full scope of alerts and malicious activity.

  
Here we can observe the dashboard, after 8 minutes or so, we will have 5 alerts

<img width="1438" height="729" alt="Captura de pantalla 2026-05-03 a la(s) 2 24 58 p m" src="https://github.com/user-attachments/assets/c7fe25e8-741b-4072-b7a6-3c1c91dfbc79" />


In order to manage the alert we need to move to the "alert queue"


<img width="1443" height="724" alt="Captura de pantalla 2026-05-03 a la(s) 2 28 21 p m" src="https://github.com/user-attachments/assets/a9fdf193-a0e9-4b79-a82c-6235d9bd6347" />


After we take ownership of the alert from the pishing email, we will proceed to analyze the domain of the sender of that email 

<img width="1129" height="492" alt="Captura de pantalla 2026-05-03 a la(s) 2 37 56 p m" src="https://github.com/user-attachments/assets/b266e8dd-6c54-455c-ad8d-c5eef99b2eb5" />


After searching it in Splunk we can observe 2 events, 2 emails sent from that email address

<img width="1454" height="750" alt="Captura de pantalla 2026-05-03 a la(s) 2 42 02 p m" src="https://github.com/user-attachments/assets/17babaec-bf40-470f-b3c8-24e66925a535" />


Lets run this domain in Virustotal to see if it is flagged 


<img width="1470" height="639" alt="Captura de pantalla 2026-05-03 a la(s) 3 25 30 p m" src="https://github.com/user-attachments/assets/45ed6a15-a655-4060-8e0c-497cd5a5e72b" />


We will close this incident report as false positive and leave a note why so

<img width="1118" height="381" alt="Captura de pantalla 2026-05-03 a la(s) 3 28 00 p m" src="https://github.com/user-attachments/assets/be86d536-0817-4fe8-909b-c5c318943f31" />


Ans that is how we solved our first alert 

<img width="1431" height="753" alt="Captura de pantalla 2026-05-03 a la(s) 3 29 08 p m" src="https://github.com/user-attachments/assets/e8148f2c-b222-40b4-98a0-4044135a4787" />

