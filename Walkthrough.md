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


And that is how we solved our first alert 

<img width="1431" height="753" alt="Captura de pantalla 2026-05-03 a la(s) 3 29 08 p m" src="https://github.com/user-attachments/assets/e8148f2c-b222-40b4-98a0-4044135a4787" />

___

## Now we will handle our firewall alert

<img width="1533" height="506" alt="Captura de pantalla 2026-05-08 a la(s) 12 01 21 a m" src="https://github.com/user-attachments/assets/1e8b832e-e1fd-46fe-a72e-d7c683604d9e" />

Our first red flag is a shortened **http** link instead of being a https

<img width="1537" height="519" alt="Captura de pantalla 2026-05-08 a la(s) 12 07 31 a m" src="https://github.com/user-attachments/assets/5a0bc65c-f089-45bc-a49e-9034f8462eb7" />

First we will run both IP addresses on Splunk, (*SourceIP* and *DestinationIP*) searching for any previous alerts on events


## SourceIP: (just the current event)
<img width="1007" height="685" alt="Captura de pantalla 2026-05-08 a la(s) 12 10 38 a m" src="https://github.com/user-attachments/assets/d2327ca5-4e93-4b04-95ee-5a3529d5d87a" />

## DestinationIP: (urrent event as well)

<img width="949" height="676" alt="Captura de pantalla 2026-05-08 a la(s) 12 11 57 a m" src="https://github.com/user-attachments/assets/90010f07-2e87-4bc8-8147-38848f5b994e" />

Next step will by analyzing that link (without opening) in VirusTotal

<img width="1919" height="522" alt="Captura de pantalla 2026-05-08 a la(s) 12 17 04 a m" src="https://github.com/user-attachments/assets/5673e507-09a1-4786-9fd8-a2dd99c26d33" />

Indeed it is pishing attempt, we will mark it as such

<img width="1579" height="585" alt="Captura de pantalla 2026-05-08 a la(s) 12 18 02 a m" src="https://github.com/user-attachments/assets/107fc030-6983-44a7-84a2-94125d52528d" />

and write our case report

<img width="1486" height="789" alt="Captura de pantalla 2026-05-08 a la(s) 12 23 10 a m" src="https://github.com/user-attachments/assets/bd984c90-60f0-4b58-a790-c317d9989426" />

Another suspicious alert is the following, were the email domain does not seems legit *m1crosoftsupport.co* and IP address *102.89.222.14* seems supicious: 

<img width="1584" height="563" alt="Captura de pantalla 2026-05-08 a la(s) 12 36 35 a m" src="https://github.com/user-attachments/assets/70413057-ea87-4bd7-a606-8bd71be36b5e" />

After searching the IP address we can confirm the malicious IP

<img width="852" height="601" alt="Captura de pantalla 2026-05-08 a la(s) 12 39 10 a m" src="https://github.com/user-attachments/assets/a2abccef-81dd-4efe-9703-5c928a65932a" />

We did it!

<img width="1329" height="423" alt="Captura de pantalla 2026-05-08 a la(s) 12 46 13 a m" src="https://github.com/user-attachments/assets/59dc613b-be73-403e-b059-617e830dcf2a" />


