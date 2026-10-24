# HTTP observations (Lab 4, Task 1)
 
| Question | My answer |
|----------|-----------|
| Request method for index.html | GET |
| Status code with Disable cache ticked | 200 OK |
| Status code on a normal reload | 304 Not Modified |
| Status code for /nothing-here.html | 404 Not Found |
| Value of the Content-Type response header | text/html; charset=utf-8 |
| Remote Address (IP and port) | IP: 127.0.0.1:5500 and port: 80 |
| Protocol in the address bar (http or https) | http |
 
## Why is this address http and not https?
The address is http because the traffic never leaves your local computer. The attacker can't intercept in the traffic through any network transit.

## Selectors I used
| Selector kind | Example from my CSS |
|---------------|---------------------|
| Element | body |
| Class | .card |
| ID | #main |
| Grouping (comma) | h1, h2, h3 |
| Descendant (space) | .nav-list a |
| Child (>) | form>fieldset |
| Adjacent sibling (+)  | h1+p |
| Compound (no space, such as a.active)  | .nav-list a.active (the a.active part) |
| Attribute	| a[href^="http"] |
| Pseudo-class | a:hover |
| Pseudo-element | .menu-group h2::before |

## Bug log (Lab 4, Task 6)
 
| # | What was wrong (file and line) | Which tool showed it | My fix |
|---|--------------------------------|----------------------|--------|
| 1 | At line 8 of bugs.html: href="style.css" | Network tab | href="bugs.css" |
| 2 | At line 14 of bugs.css:  linecolour: #ffffff; | Styles pane | linecolor: #ffffff;  |
| 3 | At line 19 of bugs.html: <h4>Today's special</h4> | Accessibility tree | <h2>Today's special<h2> |
| 4 | At line 23 of bugs.html: <label for="mail"> | LightHouse | <label for="email"> |
| 5 | At line 20 of bugs.html, the image element doesn't have the alt | W3C validator | <img src="../images/logo.svg" alt="" width="80" height="80"> |
| 6 | At line 2 of bugs.html: <html> | W3C validator | <html lang="en"> |
| 7 | At line 21 of bugs.css, there was no semicolon between two attributes | Saw the Red Signal in VS code | Added semicolon between them |
| 8 | At line 24 of bugs.html, there was no autocomplete in email | Issues tab | Added autocomplete="off" |
| 9 | At line 25 of bugs.css, there was misspelled class name | Fixed  by just reviewing the css | .notes -> .note |
| 10 | At line 12 of bugs.html: <div class="menu"> | Accessibility tree | <nav class="menu"> |