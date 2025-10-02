# Gobuster Lab

## Concept
Gobuster is a command-line brute-force tool. It tries all possible combinations to find directories/files on a target URL.

## Execution
Open a terminal and run:

```bash
gobuster -u http://example1234.com -w wordlist.txt dir
```
- **-u** → specifies the target URL  
- **-w** → specifies the wordlist to use 

## Example wordlist:
- admin
- login
- images
- secret

## Gobuster tests:
- http://example1234.com/admin 
- http://example1234.com/login
- http://example1234.com/images
- http://example1234.com/secret
<br>

> [!NOTE]   
For each word in the wordlist, Gobuster appends it to the target URL and sends a request.
It then checks the HTTP status code to determine if the resource exists or how it responds.
<br>

## HTTP Status Codes
| Code | Meaning |
|------|---------|
| 200  | OK – Resource exists and was loaded successfully |
| 204  | No Content – Resource exists but has no response body |
| 301  | Moved Permanently – Permanently redirects to another URL |
| 302  | Found / Temporary Redirect – Temporarily redirects |
| 307  | Temporary Redirect (strict) – Maintains HTTP method (e.g., POST remains POST) |
| 403  | Forbidden – Resource exists but access is denied |

## Output

The final output shows only the paths that exist on the target server.
This allows you to identify valid directories or files without manually checking each one.  
<br>

> [!TIP]
> - Use a curated wordlist to improve speed and accuracy.  
> - Combine with other reconnaissance tools for comprehensive testing.  
> - Always have permission to test the target URL to avoid legal issues.
