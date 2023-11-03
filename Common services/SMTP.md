25/tcp    open  smtp?
| smtp-commands: REEL, SIZE 20480000, AUTH LOGIN PLAIN, HELP
|_ 211 DATA HELO EHLO MAIL NOOP QUIT RCPT RSET SAML TURN VRFY

Simple mail transfer protocol
### Connect to SMTP
```
telnet ip-address port
```

### smtp-commands: 
This section provides information about the SMTP commands that the SMTP service supports. 
Each line represents a supported SMTP command:
1. REEL: An SMTP command for requesting the expansion of an email address. It is used to verify the validity of an email address.
2. SIZE 20480000: This indicates that the SMTP server supports the "SIZE" extension, which specifies the maximum message size that the server can accept.
3. AUTH LOGIN PLAIN: These are authentication mechanisms supported by the SMTP server. "AUTH LOGIN" and "AUTH PLAIN" are common methods for authenticating with an SMTP server.
4. HELP: The "HELP" command is used to request information about available SMTP commands and their usage.

211 DATA HELO EHLO MAIL NOOP QUIT RCPT RSET SAML TURN VRFY: These are SMTP commands that the server supports. For example, "DATA" is used to start the data transfer phase of an email message, "EHLO" and "HELO" are used for identifying the client to the server, "MAIL" is used to specify the sender's address, "QUIT" is used to close the SMTP session, and so on.
### An example
![image](https://github.com/Miranda-Bai/Ying_Notes/assets/120993025/667315d6-5ad0-49f4-971f-313fddfc8491)


220 Mail Service ready: This is the SMTP server's initial response, indicating that it is ready to accept SMTP commands.

HELO ying@mail.com: The HELO command is used to identify the client to the server. In this case, you're using "ying@mail.com" as the identification.

250 Hello.: The server responds with "Hello" to acknowledge the client's identification.

MAIL FROM: <ying@mail.com>: This is the "MAIL FROM" command, which specifies the sender's email address.

250 OK: The server acknowledges the sender's email address.

RCPT TO: <mico@htb.com>: This is the "RCPT TO" command, which specifies the recipient's email address.

550 Unknown user: The server responds with "Unknown user" for the recipient, indicating that it does not recognize the recipient's email address.

Subsequent RCPT TO commands follow the same pattern for different recipient email addresses.

In this interaction, you are essentially simulating the process of sending an email through an SMTP server. However, the server responds with "Unknown user" for the recipient address <ying@mail.com>, indicating that it does not have a user with that email address.

### SMTP User Enumeration

[smtp-user-enum](https://pentestmonkey.net/tools/user-enumeration/smtp-user-enum) by pentestmonkey

#### Install dependencies:
   ```
   # perl -MCPAN -e shell
   cpan> install Getopt::Std
   ```
Dependencies:
    
    Socket
    
    IO::Handle
    
    IO::Select
    
    IO::Socket::INET
    
    Getopt::Std
   
![image](https://github.com/Miranda-Bai/Ying_Notes/assets/120993025/9df1fb27-dcd2-4f74-b395-f07b96553eed)

#### Download smtp-user-emnu and copy it to /usr/bin/
 
