# THMHydra

## Overview
This is the work of Huwaina Yasmin binti Anuar Asfandi, student ID: 52215124317, class: Vulnerability Analysis: L01-B02. 
Hydra is a fast and flexible login cracker used to brute force credentials across multiple protocols.

---

## Setup
1. Start intercepting traffic in http://MACHINE_IP using Burp Suite. Make sure to use Burp's preconfigured browser, which automatically directs traffic through the proxy. Click on 'Open Browser' to use Burp's browser, and start the TryHackMe machine in Burp's browser.
<img width="772" height="478" alt="image" src="https://github.com/user-attachments/assets/55d1b228-9f66-4249-99d1-96653a6a5fb5" />

2. Input anything into the username and password fields to let Burp intercept.
<img width="772" height="694" alt="image" src="https://github.com/user-attachments/assets/85cbef51-77b1-490d-b8c4-74ac7282838a" />

3. Use the underlined line for our next step
<img width="1196" height="712" alt="image" src="https://github.com/user-attachments/assets/8619563d-91f8-4541-8c2e-739271a9520e" />

4. Navigate to the root user and use the following command to run hydra.
```bash
hydra -l molly -P /usr/share/wordlists/rockyou.txt 10.49.134.28 http-post-form "/login:username=^USER^&password=^PASS^:Your username or password is incorrect."
```
<img width="1662" height="186" alt="image" src="https://github.com/user-attachments/assets/ed6283f5-a39a-4748-aea0-877d203c886b" />
<img width="1662" height="186" alt="image" src="https://github.com/user-attachments/assets/1dcc14e3-dc87-4c17-b3f0-6a12293a4fca" />





