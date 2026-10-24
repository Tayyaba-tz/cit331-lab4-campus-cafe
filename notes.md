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

## Live site observations (Lab 4, Task 7)
 
1. Compare localhost (Task 1) with the live site: protocol, server header, and
   Remote Address. What changed and why?

   - Protocol: localhost (http://127.0.0.1:5500/index.html) uses http. The live site (https://tayyaba-tz.github.io/cit331-lab4-campus-cafe/) uses https.
   - Server header: on localhost it is the local development server (Live Server). On the live site it is GitHub.com, because GitHub Pages hosts the site.
   - Remote Address: on localhost it is 127.0.0.1:5500, which is my own computer. On the live site it is a public GitHub Pages IP address (usually one that starts with 185.199.108 to 185.199.111) on port 443.
   - Why it changed: on localhost the browser and the server are on the same computer, so the traffic never leaves it. On the live site the traffic goes across the internet to GitHub's servers. This is why the site uses https and port 443, and why the response comes from GitHub's server software and not from my local tool.

2. What does the padlock and certificate tell the visitor, and what could an
   attacker on the same Wi-Fi do if the site were plain http?

   - The padlock tells the visitor that the connection to tayyaba-tz.github.io is encrypted with TLS. The certificate shows that a trusted certificate authority checked the domain name, and that the certificate is still valid.
   - It does not prove the site is honest. It only proves that the visitor is talking to the real owner of that domain, and that nobody can read the data on the way.
   - If the site were plain http, an attacker on the same Wi-Fi could read what I send and receive, such as form data and cookies. They could also change the page on the way (for example, add a fake form or a malicious script) or send me to a fake copy of the site.

3. Why was the Saved orders table empty on the live site, even though you saved
   orders on localhost? (Hint: storage belongs to an origin.)

   - Browser storage belongs to one origin. An origin is the protocol, the domain name and the port together.
   - http://127.0.0.1:5500 and https://tayyaba-tz.github.io are two different origins, so they cannot see each other's data. The orders I saved on localhost stayed in my browser under the localhost origin. They were never sent to a server, so the live site started with empty storage.

4. Which HTTP status code did the missing page return, and who sent it?

   - The missing page returned status code 404 Not Found.
   - It was sent by the GitHub Pages server (Server: GitHub.com), not by the browser. The page I saw was GitHub's own 404 page.