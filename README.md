<h1>Simulation - Network attack analysis</h1>

 ### You can also read this in: [Português](https://github.com/GLMello/Analise-Atq-Sim)

<h2>Description</h2>
This project consists of analyzing a network attack simulation, identifying the kind of attack and explaining how it affected the targeted web page.

<br />


<h2>Scenario</h2>
You work as a security analyst for a travel agency that advertises sales and promotions on the company’s website. The employees of the company regularly access the company’s sales webpage to search for vacation packages their customers might like. 

One afternoon, you receive an automated alert from your monitoring system indicating a problem with the web server. You attempt to visit the company’s website, but you receive a connection timeout error message in your browser.

You use a packet sniffer to capture data packets in transit to and from the web server. You notice a large number of TCP SYN requests coming from an unfamiliar IP address. The web server appears to be overwhelmed by the volume of incoming traffic and is losing its ability to respond to the abnormally large number of SYN requests. You suspect the server is under attack by a malicious actor. 

You take the server offline temporarily so that the machine can recover and return to a normal operating status. You also configure the company’s firewall to block the IP address that was sending the abnormal number of SYN requests. You know that your IP blocking solution won’t last long, as an attacker can spoof other IP addresses to get around this block. You need to alert your manager about this problem quickly and discuss the next steps to stop this attacker and prevent this problem from happening again. You will need to be prepared to tell your boss about the type of attack you discovered and how it was affecting the web server and employees.

<h2>Resources </h2>

 ### [TCP/HTTP log](https://docs.google.com/spreadsheets/d/1PGqx7XkiAq2m5147FqyZ06JhLyrprZ0mQvwBBk8vJ_I/template/preview)

<h2>Walk-through</h2>

<p align="left">
By analyzing the log I noticed the following connection attempts:
  <br/><br />
<img src="https://i.imgur.com/mb3ijXT.png" height="55%" width="55%" alt="Abnormal connections"/>
<br /><br />
This behavior goes on until the web server gets overloaded and ends up unable to respond to any connections.
<br /><br />
<img src="https://i.imgur.com/GbTdY1T.png" height="55%" width="55%" alt="Agravação"/>
<br /><br />
Following that, I decided to analyze the abnormal logs individually.
I was then able to notice two common factors between them: The origin IP address and the kind of packet that was sent. 
  <br/><br />
<img src="https://i.imgur.com/4EzNKAl.png" height="55%" width="55%" alt="Padrão"/>
<br /><br />
Henceforth, I was able to deduce that the attack was of the DoS SYN flood attack, since it originated from a single IP address and used exclusevely SYN requests.
<br/><br />
The final step was to come up with a report by using the deducted data along with the scenario information.
<br /><br />
<img src="https://i.imgur.com/yr793sv.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<h2>Note</h2>

 This project was part of the course [Google Cybersecurity Professional Certificate](https://www.coursera.org/professional-certificates/google-cybersecurity) course. <br />
