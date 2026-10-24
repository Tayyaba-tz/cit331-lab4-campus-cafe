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