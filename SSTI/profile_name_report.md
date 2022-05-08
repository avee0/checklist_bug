https://hackerone.com/reports/125980

Hi, Uber Security Team
I found an RCE in rider.uber.com.
First, if you change your profile name to {{ '7'*7 }}, and you will receive a mail
"Your Uber account information has been updated"
sent by support@uber.com
And in mail body, you can see your name become '7777777'
This is a vulnerability about Flask Template Engine(Jinja2) Injection , more detail can be seen in these blogs
https://nvisium.com/blog/2016/03/09/exploring-ssti-in-flask-jinja2/
https://nvisium.com/blog/2016/03/11/exploring-ssti-in-flask-jinja2-part-ii/
I think it can be a Remote Code Execution vulnerability but there is a length limit :(
But I still can "write" some Python code in "name" filed, there are more examples in attachments and bellow are my payloads
{{ '7'*7 }}
{{ [].class.base.subclasses() }} # get all classes
{{''.class.mro()[1].subclasses()}}
{%for c in [1,2,3] %}{{c,c,c}}{% endfor %}
...
Thanks for your patience for reading my report. : )
