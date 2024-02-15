General
What authentication means
What session authentication means
What Cookies are
How to send Cookies
How to parse Cookies

Cookie
The Cookie HTTP request header contains stored HTTP cookies associated with the server (i.e. previously sent by the server with the Set-Cookie header or set in JavaScript using Document.cookie).

The Cookie header is optional and may be omitted if, for example, the browser's privacy settings block cookies.

Header type	  Request header
Forbidden header name	  yes
Syntax
HTTP
Copy to Clipboard
Cookie: <cookie-list>
Cookie: name=value
Cookie: name=value; name2=value2; name3=value3
Directives
<cookie-list>
A list of name-value pairs in the form of <cookie-name>=<cookie-value>. Pairs in the list are separated by a semicolon and a space ('; ').

Examples
HTTP
Copy to Clipboard
Cookie: PHPSESSID=298zf09hf012fh2; csrftoken=u32t4o3tb3gg43; _gat=1
Specifications
Specification
HTTP State Management Mechanism
# cookie