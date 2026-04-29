# THMHydra

## Overview
This is the work of Huwaina Yasmin binti Anuar Asfandi, student ID: 52215124317, class: Vulnerability Analysis: L01-B02. 
Hydra is a fast and flexible login cracker used to brute force credentials across multiple protocols.

---

## Walk-through
1. Start intercepting traffic in http://MACHINE_IP using Burp Suite. Make sure to use Burp's preconfigured browser, which automatically directs traffic through the proxy. Click on 'Open Browser' to use Burp's browser, and start the TryHackMe machine in Burp's browser.
<img width="772" height="478" alt="image" src="https://github.com/user-attachments/assets/55d1b228-9f66-4249-99d1-96653a6a5fb5" />

2. Input anything into the username and password fields to let Burp intercept.
<img width="772" height="694" alt="image" src="https://github.com/user-attachments/assets/85cbef51-77b1-490d-b8c4-74ac7282838a" />

3. Use the underlined line for our next step.
<img width="1196" height="712" alt="image" src="https://github.com/user-attachments/assets/8619563d-91f8-4541-8c2e-739271a9520e" />

4. Navigate to the root user and use the following command to run hydra. Upon running, we can get the password for the username molly, which is 'sunshine'.
```bash
hydra -l molly -P /usr/share/wordlists/rockyou.txt <TARGET_IP> http-post-form "/login:username=^USER^&password=^PASS^:Your username or password is incorrect."
```
<img width="1662" height="186" alt="image" src="https://github.com/user-attachments/assets/ed6283f5-a39a-4748-aea0-877d203c886b" />

5. Log in using the credentials recently acquired
<img width="1383" height="760" alt="image" src="https://github.com/user-attachments/assets/a0fcba01-c604-42a5-9087-0ba304f02ea1" />

6. This is the screen displayed upon logging in
<img width="1919" height="847" alt="image" src="https://github.com/user-attachments/assets/3674b665-75c8-4b6a-aceb-ac19b22d1b31" />

7. Next, use hydra for the SSH file using the following command. Upon running, we can get the password for the SSH file: butterfly
```bash
hyrda -l molly -P /usr/share/wordlists/rockyou.txt 10.49.134.28
``` 
<img width="1274" height="291" alt="image" src="https://github.com/user-attachments/assets/3604bfa7-dc43-48f1-b500-e7d78a11a036" />

8. Now access the SSH file using the password acquired using the following command. Type in 'yes' to continue
```bash
ssh molly@<TARGET_IP>
```
<img width="947" height="727" alt="image" src="https://github.com/user-attachments/assets/2c01139e-0325-447e-90c3-83a69b3f0abc" />

9. Once inside the SSH, use the command 'ls' to display every file, and we will find a 'flag2.txt' file.
<img width="229" height="39" alt="image" src="https://github.com/user-attachments/assets/181384d6-ec63-4f2b-bebf-f2a8cf2cc530" />

10. Next, use the command 'cat' to display the contents of the 'flag2.txt' file. We will get the second flag: THM{c8eeb0468febbadea859baeb33b2541b}
<img width="309" height="39" alt="image" src="https://github.com/user-attachments/assets/00b5301d-b4a7-4612-880d-9b340eb03b73" />

> I completed this room with the help of this YouTube video: https://youtu.be/8fs_7bm88GY?si=LYBvq31-q6vAOv74
