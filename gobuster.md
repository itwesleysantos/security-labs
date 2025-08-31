# Gobuster

## Concept
The Gobuster application is a command-line application, meaning it lacks a graphical user interface. <br>
It is also a brute force tool, that is, a tool whose method is to try all possible combinations until finding the correct one.

## Execution
With the terminal open, type gobuster -u http://example1234.com -w wordlist.txt dir <br>
The -u defines the target URL to be tested (http://example1234.com). <br>
The -w defines the wordlist with the names that Gobuster will use to try to find directories/files (wordlist.txt).

## How it happens
In other words, it will take each word from the wordlist.txt file and append it to the URL http://example1234.com/ to see if it exists.

If wordlist.txt contains, for example: <br>
admin <br>
login <br>
images <br>
secret

Gobuster will assemble and test these URLs: <br>
http://example1234.com/admin <br>
http://example1234.com/login <br>
http://example1234.com/images <br>
http://example1234.com/secret
<br>
<br>
For each request, it checks the HTTP status:
- 200 (OK) → Resource exists and was loaded successfully.
- 204 (No Content) → Resource exists, but has no response body (an "empty" page).
- 301 (Moved Permanently) → Permanently redirects to another URL.
- 302 (Found / Temporary Redirect) → Temporarily redirects.
- 307 (Temporary Redirect, strict) → Temporarily redirects, but maintains the HTTP method (e.g., POST remains POST).
- 403 (Forbidden) → The resource exists, but you don't have permission to access it.

In the end, you have a list of only the paths that actually exist on the target.
