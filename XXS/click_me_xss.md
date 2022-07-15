click me xss:


  1.  You need a web server, put poc.html (F1722320) to www
  2.  visit it: http://<host>:<port>/poc.html?x=${alert(1)}
  3.  click it
  4.  you will see the alert

#### Impact
  
Cookie Stealing - A malicious user can steal cookies and use them to gain access to the application.
Arbitrary requests - An attacker can use XSS to send requests that appear to be from the victim to the web server.
Malware download - XSS can prompt the user to download malware. Since the prompt looks like a legitimate request from the
site, the user may be more likely to trust the request and actually install the malware.
Defacement - attacker can deface the website usig javascript code.
  
