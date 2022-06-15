payloads:

"/><img src="x"><a href="https://evil.com">login</a>
"><img src="x">



reports:


While testing "account.acronis.com", I found that "first name" could be injected with HTML tags while sending an email invitation. But this attack requires user interaction to confirm the email first, then he/she will receive a welcome email "Welcome to your Acronis Cyber Protect trial!" Contains the injected payload!

Steps to Reproduce:

   1. Please register at https://www.acronis.com/en-us/products/cyber-protect/trial/#registration with the victim's email.
   2. Inject "First Name" field with HTML tags, for example: "/><img src="x"><a href="https://evil.com">login</a>.
      Check the email inbox, HTML tags will be executed. "Your Acronis Cyber Protect trial starts today!"

Reference:
https://hackerone.com/reports/1536899

