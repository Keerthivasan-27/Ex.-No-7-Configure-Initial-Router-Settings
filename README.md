## Ex. No: 7 – Configure Initial Router Settings
# Date: ____24/11/2026_______
KEERTHIVASAN A
212223060124
________________________________________
# Objective
To perform basic router configuration tasks in Cisco Packet Tracer including:<br>
•	Verifying the default router configuration.<br>
•	Configuring initial router settings (hostname, MOTD, passwords).<br>
•	Securing access to the CLI and console port.<br>
•	Encrypting passwords.<br>
•	Verifying and saving the configuration to NVRAM and flash.<br>
________________________________________<br>
# Apparatus/Tools Required
•	Cisco Packet Tracer<br>
•	1 Router (R1 – 2911 or equivalent)<br>
•	1 PC (for console connection)<br>
•	Console cable (RS-232 to Console)<br>
________________________________________<br>
# Network Topology Diagram
<img width="1917" height="1078" alt="Screenshot 2026-11-24 152828" src="https://github.com/user-attachments/assets/e652043c-d065-47d0-99e4-660f4c6db0ff" />

________________________________________
# Procedure
# Part 1: Verify the Default Router Configuration
1.	Connect PC → Router R1 using a Console cable.<br>
2.	On PC → Desktop → Terminal → Connect to R1.<br>
3.	Enter privileged EXEC mode:<br>
4.	Router> enable<br>
5.	Router#<br>
6.	Display running configuration:<br>
7.	Router# show running-config<br>
o	Observe hostname, interfaces, vty lines.<br>
8.	Display startup configuration:<br>
9.	Router# show startup-config<br>
o	Router shows: startup-config is not present (because nothing is saved in NVRAM yet).<br>
________________________________________
# Part 2: Configure and Verify Initial Router Configuration
1.	Enter global configuration mode:<br>
2.	Router# configure terminal<br>
3.	Configure hostname:<br>
4.	Router(config)# hostname R1<br>
5.	Configure MOTD banner:<br>
6.	R1(config)# banner motd # Unauthorized access is strictly prohibited #<br>
7.	Configure passwords:<br>
o	Console password:<br>
o	R1(config)# line console 0<br>
o	R1(config-line)# password letmein<br>
o	R1(config-line)# login<br>
o	R1(config-line)# exit<br>
o	Enable password (unencrypted):<br>
o	R1(config)# enable password cisco<br>
o	Enable secret (encrypted):<br>
o	R1(config)# enable secret itsasecret<br>
8.	Encrypt all plain-text passwords:<br>
9.	R1(config)# service password-encryption<br>
10.	Exit and verify login prompts:<br>
o	On exit, router shows MOTD.<br>
o	User is prompted for password.<br>
o	Enter letmein (console) → access User EXEC mode.<br>
o	Enter itsasecret → access Privileged EXEC mode.<br>
________________________________________
# Part 3: Save the Running Configuration
1.	Save running configuration to NVRAM:<br>
2.	R1# copy running-config startup-config<br>
Short version:<br>
R1# wr<br>
3.	Verify NVRAM contents:<br>
4.	R1# show startup-config<br>
o	Confirms saved configuration.<br>
5.	Save startup config to flash (backup):<br>
6.	R1# copy startup-config flash<br>
o	Use show flash to verify file stored in flash.<br>
________________________________________
# Commands Used
•	To enter privileged mode: enable<br>
•	To view config: show running-config, show startup-config<br>
•	To configure hostname: hostname<br>
•	To configure MOTD banner: banner motd<br>
•	To set passwords: enable password, enable secret, line console<br>
•	To encrypt passwords: service password-encryption<br>
•	To save configuration: copy running-config startup-config, wr, copy startup-config flash<br>
________________________________________
# Output (Attach Screenshots)
•	Console connection to router<br>
<img width="1917" height="1078" alt="Screenshot 2026-11-24 152828" src="https://github.com/user-attachments/assets/e652043c-d065-47d0-99e4-660f4c6db0ff" />
•	Running configuration before and after<br>
<img width="1902" height="1077" alt="image" src="https://github.com/user-attachments/assets/1fd4572f-ee6f-4cb3-badd-c80170d7b8d6" />

•	MOTD banner display<br>
<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/ecd582d4-5637-4392-bcf8-ae5a6a4db833" />

•	Password prompts<br>
<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/adc0e4a7-a47e-4254-a847-85ea6a421c07" />

•	Saved configuration in NVRAM and flash<br>
<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/c342242d-c322-4334-886a-da9b4c5c5dd0" />

________________________________________
# Result
The router was successfully configured with hostname, banner, encrypted passwords, and secure console access. The configuration was verified and saved to NVRAM and flash, ensuring persistence across reboots.

