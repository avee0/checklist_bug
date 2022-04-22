Web cache poisoning:

In this attack attacker exploit the behaviour of web server and cache server so that attacker can serve malicious web pages to odinary users.

2 phase:
1. attacker must workout how elicit a response from the back end server
2. make user your response is cached

web cache poisoning lead to javascript injection, open redirect, xss and etc:

cache keys:
cache identify equivalent request by comparing a predefinded subset of request component know as cache key.
unkeyed:
component that are not include in cache keys said to be unkeyed.

Constructing attack:
1. identify and rvalute unkeyed input.
2. elicit a harmful response from the back end server.
3. get the response cached

1. Identify and revalute unkeyed inputs.
The attack relias on manipulation of unkeyed header because cache server ignore the unkeyed header when deciding whether to server cached response 
therefor first step is to constructing a web cache attack is to identifying unkeyed input that are supported by the server.

2. Elicit a harmfull response from the backend server.
once first step is done our next step is to manupulate input and elicit harmfull response.

3. Get response cached 
