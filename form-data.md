# Sending form data

from https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_and_retrieving_form_data

> At it's most basic, the web uses a client/server architecture that can be summarized as follows. a client (usually a web browser) sends a request to a server (most of the time a web server like Apache, Nginx, IIS, Tomcat, etc.), using the HTTP protocol. The server answers the request using the same protocol.
 
incoming data is passed name=value pairs that map back to the name and values of form controls.

you can see http requests under the "network" tab within the dev tools by going to:

1: "All"
2: "<your-url>.com" in the "Name" tab
3: "Headers"

Sensitive or large data should always be sent of a POST.

from: https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_and_retrieving_form_data#security_issues

> All data that comes to your server must be checked and sanitized. Always. No exception.

> - Escape potentially dangerous characters. The specific characters you should be cautious with vary depending on the context in which the data is used and the server platform you employ, but all server-side languages have functions for this. Things to watch out for are character sequences that look like executable code (such as JavaScript or SQL commands).
> - Limit the incoming amount of data to allow only what's necessary.
> - Sandbox uploaded files. Store them on a different server and allow access to the file only through a different subdomain or even better through a completely different domain.
 
Data can be validated on client side but even so must always be validated within the server. There is know way of knowing that the client actually sent clean data.
