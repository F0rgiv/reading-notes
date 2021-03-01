# EJS

ejs is a view engine used for templating on the server before serving the pages.

layout file can be used for templating, then enables you to create a single maintained template file that contains static data like a header or nav bar that doesn't need to be recoded on each html page.

insert snipit
```<%- include('<some other chick of html>'); %>```

if loop
```<% if (user) { %>
  <h2><%= user.name %></h2>
<% } %>
```
