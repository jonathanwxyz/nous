#Distributed-Systems 

### What is it?
- Like [[HTTP]], the Simple Mail Transport Protocol (SMTP) is a text-based [[Protocols|protocol]] used for [[Email]]
- Unlike HTTP, it is ==connection based==
	- A client (in this case, the Mail User Agent) can issue multiple consecutive comments to the SMTP server and should explicitly terminate its connection when its finished

### Example email exchange
```
01 S: 220 smtp.example.com ESMTP Postfix  
02 C: HELO relay.example.org  
03 S: 250 Hello relay.example.org, I am glad to meet you  
04 C: MAIL FROM:<bob@example.org>  
05 S: 250 Ok  
06 C: RCPT TO:<alice@example.com>  
07 S: 250 Ok  
08 C: RCPT TO:<theboss@example.com>  
09 S: 250 Ok  
10 C: DATA  
11 S: 354 End data with <CR><LF>.<CR><LF>  
12 C: From: "Bob Example" <bob@example.org>  
13 C: To: "Alice Example" <alice@example.com>  
14 C: Cc: theboss@example.com
15 C: Date: Tue, 15 January 2008 16:02:43 -0500  
16 C: Subject: Test message  
17 C:  
18 C: Hello Alice.  
19 C: This is a test message with 5 header fields and 4 lines in the message body.  
20 C: Your friend,  
21 C: Bob  
22 C: .  
23 S: 250 Ok: queued as 12345  
24 C: QUIT  
25 S: 221 Bye  
{The server closes the connection}
```
C - Client
S - Server
At the end of this exchange, Bob’s email has successfully been moved from his mail client, to his ‘outgoing mail server’.