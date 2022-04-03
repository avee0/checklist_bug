account lockout is implemented but not in secure way. 

After we exceeed rate limit our account is locked out which means taht all sessions are terminated.

Once it happens, all sessions will be terminated even the session in which victim was logged in!

The secure way of implementting is to not destroy currrent logged in session

The reasons are:
- Victim wont ever bruteforse his/her own account password
- There is no reason to terminate logged in session as the attacker dont even access to account. 

step:
1. login as victim in mobile or other device
2. as attacker bruteforce password in victim account.
3. account will be locked out and all the session will be destroy.
4. victim account will be logout and victim wont be able to login.

Reference:
https://link.medium.com/dc29sOwWUob
by akash hamal
