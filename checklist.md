## 1. Information Gathering
### a. Subdomain enumeration
- Sublis3tr
- Subfinder
- SubEnum
### b. Checking live hosts
- Httpx
### c. Checking status code
- httpstatus.io 
### d. Recon
- Source code view
- Check JS files
- Way-back URL (web archive)
- Google Dorking
- Bug Bounty Helper (https://dorks.faisalahmed.me/#)
- GitHub Dorking


## 2. Critical File Vulnerability
- Dirb
- If got 403, then use 403 bypasser (https://github.com/iamj0ker/bypass-403)


## 3. Host Header Injection
### Chain Bugs:
- HHI ----> Password Reset Poisoning
- HHI ----> Password Reset Poisoning via dangling markup (Host: target.com:'<a href="//bing.com/?)
- HHI ----> Web cache poisoning
```
    I. Web Cache Poisoning ----> XSS
    II. Web Cache Poisoning ----> Open Redirection
    III. Web Cache Poisoning ----> Open Redirection ----> Dos
```
### Payloads:
>I. Change the host header
- Host: vulnerable-website.com ----> evil-website.com
    
>II. Duplicating the host header
- GET /index.php HTTP/1.1 
- Host: vulnerable-website.com 
- Host: evil-website.com
    
>III. Add host override headers
- X-Forwarded-For: evil-website.com 
    X-Forwarded-Host: evil-website.com 
    X-Client-IP: evil-website.com 
    X-Remote-IP: evil-website.com 
    X-Remote-Addr: evil-website.com 
    X-Host: evil-website.com

>IV. Add line wrapping
- GET /index.php HTTP/1.1 
    Host: vulnerable-website.com
    Host: evil-website.com

>V. Supply an absolute URL
- GET https://vulnerable-website.com/ HTTP/1.1 
    Host: evil-website.com


## 4. Automation
- Nuclei


## 5. Rate limit testing
- Profile details change, login, forgot password, comment, share, report post, tag, sending
friend request, register, contact form, Any form, 2fa submission
- Try rate limit bypass


## 6. Account Takeover
- Response Manipulation/Status code Manipulation
- Brute Force


## 7. Two Factor Authentication(2FA) BYPASS 
>Reference(https://www.youtube.com/watch?v=X2WfhBYQ2fY)
- Response Manipulation/Status code Manipulation
- Brute Force
- Token doesn't expire after usage
- Request 2 tokens from account A and B. Use the A's token in B's account
- Try to go directly to the dashboard URL without solving the 2FA. If not, success try adding the referral header to the 2FA page URL while going to dashboard
- Search the 2FA code in response
- Search the 2FA code in JS files
- CSRF/Clickjacking to disable 2FA
- Request Manipulation
- Enabling 2FA doesn't expire previous sessions


## 8. WordPress
### a. Automation
- WPScan
- CMSMap
- CMSScan
### b. XMLRPC
- SSRF - pingback.ping
1. Port Scanning
2. Origin Ip Found
- Bruteforce - wp.getUsersBlogs
### c. Application-level DOS via load-scripts.php


## 16. SSRF
### a. You have to find any parameter that may have some kind of external interaction or they can interact to external domain
- Read file from server (file:///LFI_payloads)
- Scan the Internal Network
- SSRF with RFI
  
  
## 17. Source Code Disclosure
### a. Google dork
- Site:example.com index.of.backup 
### b. Use intruder with critical file payload
  
  
## 18. CSRF
  
  
## 19. Burp Suite (Actively and Passively scan the host) 

  
## 20. Try Intercom bug

## Installation

>For Linux:
```bash
apt update
apt install git
git clone https://github.com/Mohammad-Shoab/Port-Scanner.git
```
>For windows:
we need to download the zip file and extract it.

## Usage

- For Linux: Type ```python3 port_scanner.py (ip)``` to run the tool.
- For windows: Open cmd at file location & Type ```python3 port_scanner.py (ip)``` to run the tool.

(we have to put ip without bracket like python3 port_scanner.py 127.0.x.x)

## Note

In the port scanner.py file, I had configured the port from 50 to 85 by default, but you may alter it to suit your needs.
