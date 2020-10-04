# Labs
Lab exercises in Networks.

### Simple Mail Transfer Protocol -- SMTP
SMTP is a network protocol used for transferring email messages to servers. The server should be listening at port 25. In order to send an email message you should follow the next steps (based on https://docs.microsoft.com/en-us/exchange/mail-flow/test-smtp-with-telnet?view=exchserver-2019#step-3-use-telnet-on-port-25-to-test-smtp-communication):

*In Windows you can either use the telnet program available in git-bash or install a telnet client as explained in the previous link. *

* Step 1: Install the Telnet Client on your computer
  - Windows 10: Telnet is available, you just need to enable it. 
    - Open “Control Panel“.
    - Open “Programs“.
    - Select the “Turn Windows features on or off ” option.
    - Check the “Telnet Client” box.
    - Click “OK“. A box will appear that says “Windows features” and “Searching for required files“.When complete, the Telnet client should be installed in Windows.
    Alternatively, you can execute from the command promt as administrator:
    - dism /online /Enable-Feature /FeatureName:TelnetClient

Step 2: Find the Fully Qualified Domain Naim (FQDN) or IP address of the destination SMTP server
To connect to an SMTP server by using Telnet on port 25, you need to use the fully-qualified domain name (FQDN) (for example, outlook.himolde.no) or the IP address of the SMTP server. If you don't know the FQDN or IP address, you can use the Nslookup command-line tool to find the MX record for the destination domain.
- Type nslookup -type=MX himolde.no

The output of the command looks like this:
Server:  hork.himolde.no
Address:  158.38.95.10

himolde.no      MX preference = 10, mail exchanger = outlook.himolde.no

Your mail server is the mail exchanger, that server should have a 25 port open and you can use it as the destination of your message sending request

Step 3: Use Telnet on Port 25 to test SMTP communication
In this example, we're going to use the following values. When you run the commands on your server, replace these values with ones for your organization's SMTP server, domain, etc.

Destination SMTP server: outlook.himolde.no

Source domain: gmail.com

Sender's e-mail address: chris@gmail.com

Recipient's e-mail address: youremail@himolde.no

Message subject: Test from me to me

Message body: This is a test message

 Tip

The commands in the Telnet Client aren't case-sensitive. The SMTP command verbs in this example are capitalized for clarity. You can't use the backspace key in the Telnet session after you connect to the destination SMTP server. If you make a mistake as you type an SMTP command, you need to press Enter, and then type the command again. Unrecognized SMTP commands or syntax errors result in an error message that looks like this: 500 5.3.3 Unrecognized command

Open a Command Prompt window, type telnet, and then press Enter.

This command opens the Telnet session.

Type set localecho, and then press Enter.

This optional command lets you view the characters as you type them, and it might be required for some SMTP servers.

Type set logfile <filename>, and then press Enter.

This optional command enables logging and specifies the log file for the Telnet session. If you only specify a file name, the log file is located in the current folder. If you specify a path and file name, the path needs to be on the local computer, and you might need to enter the path and file name in the Windows DOS 8.3 format (short name with no spaces). The path needs to exist, but the log file is created automatically.

Type OPEN outlook.himolde.no 25, and then press Enter.

Type EHLO gmail.com, and then press Enter.

Type MAIL FROM:<chris@gmail.com>, and then press Enter.

Type RCPT TO:<youremail@himolde.no> NOTIFY=success,failure, and then press Enter.

The optional NOTIFY command specifies the particular delivery status notification (DSN) messages (also known as bounce messages, nondelivery reports, or NDRs) that the SMTP is required to provide. In this example, you're requesting a DSN message for successful or failed message delivery.

Type DATA, and then press Enter.

Type Subject: Test from me to me, and then press Enter.

Press Enter again.

A blank line is needed between the Subject: field and the message body.

Type This is a test message, and then press Enter.

Type a period ( . ), and then press Enter.

To disconnect from the SMTP server, type QUIT, and then press Enter.

To close the Telnet session, type quit, and then press Enter.

Step 4: Success and error messages in the Telnet Session
This section provides information about the success and failure responses to the commands that were used in the previous example.



### MAC Address
How to find your interface MAC address:
Linux: 
- Type "ifconfig -a"
- From the displayed information, find your network adapter
- Locate the number next to the HWaddr. This is your MAC address.

MacOS: 
- Type "ifconfig -a"
- From the displayed information, find your network adapter
- Locate the number next to the ether. This is your MAC address.
Alternatively, you can:
- Select System Preferences from the Apple menu at the top left of your screen.
- Click Network from the System Preferences menu.
- Choose your network (Wi-Fi if you are not connected to the cable network) from the list of interfaces on the left and click the Advanced button.
- Choose the Hardware tab under which you will see the MAC address of your wireless card.

Windows: https://www.laptopmag.com/articles/find-mac-address-windows-10
