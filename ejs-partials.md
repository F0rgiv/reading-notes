# EJS Partials

Partials allow you to easily use certain ejs files as templates that can be injected into others. For example you could code your header, footer nav bar etc a single time and then inject those into each individual page's html. Not only that but maintenance becomes much simpler as you are able to simply update the partials/sample.ejs file and the changes will take effect on all pages across the entire app.

code snippets from: https://medium.com/@henslejoseph/ejs-partials-f6f102cb7433
consider the below two ejs files
```
<!-- views/partials/footer.ejs -->
<footer class="footer">
    <p>© 90210 Lawyer Stuff.</p>
</footer>
```

```
<!-- views/partials/navbar.ejs -->
<div class="header clearfix">
    <nav>
        <ul class="nav nav-pills pull-right">
            <li role="presentation"><a href="/">Home</a></li>
        </ul>
        <h3 class="text-muted">Node.js Blog</h3>
    </nav>
</div>
```
    
-----

this would enable you to have another with something like below:
```    
<body>
    <div class="container">
        <%- include('partials/navbar') %>
        <div class="jumbotron">
       ...
        </div>
        <%- include('partials/footer') %>
    </div>
</body>
 ```
    
    In this instance the navbar.ejs and footer.ejs are dynamically injected into our main page.
