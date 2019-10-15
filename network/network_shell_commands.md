## Main Ubuntu network shell commands:

1. __curl and wget:__
Use the curl or wget commands to download a file from the Internet without leaving the terminal. 
If you’re using curl, type _curl -O_ followed by the path to the file. 
_wget_ users can use _wget_ without any options.. The file will appear in the current directory.

2. __ping:__
ping sends ECHO_REQUEST packets to the address you specify. It’s a great way to see whether your computer can communicate with the Internet or a specific IP address. 
You can specify a finite amount of packets with the -c switch, by example:
_$ ping -c 4 google.com_, with this command you send 4 packets to google.com.

3. __tracepath:__
 Tracepath traces the network path to a destination you specify and reports each “hop” along the path. If you’re having network problems or slowness, tracepath can show you where the network is failing or where the slowness is occurring.
 _$ tracepath google.com_

4. __mtr:__
The _mtr_ command combines ping and tracepath into a single command. mtr will continue to send packets, showing you the ping time to each “hop.” This will also show you any problems.
_$ mtr ipDirection_

5. __host:__
The _host_ command performs DNS lookups. Give it a domain name and you’ll see the associated IP address. Give it an IP address and you’ll see the associated domain name.
_$ host ipAddress_

6. __whois:__
The whois command will show you a website’s whois records, so you can view more information about who registered and owns a specific website.
_$ whois example.com_

7. __ifplugstatus:__
The ifplugstatus command will tell you whether a cable is plugged into a network interface or not.

8. __netstat:__
The netstat command can show a lot of different interface statistics, including open sockets and routing tables. Run the netstat command with no options and you’ll see a list of open sockets.