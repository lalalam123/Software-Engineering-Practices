## Content
* [Zero Day Attack](#Zero-Day-Attack)
* [Website Defacement Attack](#-Website-Defacement-Attack-網頁置換攻擊)
* [Defacement Attack Causes](#Common-causes-of-defacement-attacks)
* [Social Engineering](#Software-Engineering)
* [HTML Injection](#HTML-Injection)
* [CSS Injection]()
* [Javascript Injection]()
* [SQL Injection]()

## Zero Day Attack
- A zero-day attack takes place when hackers exploit the flaw before developers have a chance to address it.
- Cyber criminals leverage the vulnerability to cause damage.
- Developer has only just learned of the flaw – which means they have “zero days” to fix it.
- The hacker is usually the one who discover the flaw.
- 在電腦領域中，零日漏洞或零時差漏洞通常是指還沒有修補程式的安全漏洞，而零日攻擊或零時差攻擊則是指利用這種漏洞進行的攻擊。
- 提供該漏洞細節或者利用程式的人通常是該漏洞的發現者。
- 零日漏洞的利用程式對網路安全具有巨大威脅，因此零日漏洞不但是駭客的最愛，掌握多少零日漏洞也成為評價駭客技術水準的一個重要參數。

## Website Defacement Attack 網頁置換攻擊
- Web defacement is an attack in which malicious parties penetrate a website and replace content on the site with their own messages.
- The messages can convey a political or religious message, profanity or other inappropriate content that would embarrass website owners.
- In 2012, users could not access Google Romania, and instead were taken to a defacement screen posted by MCA-CRB, the “Algerian Hacker”.
- The defacement was in place for at least an hour.
- The attack was performed by DNS hijacking—attackers managed to falsify DNS responses and redirect users to their own server instead of Google’s.

## Common causes of defacement attacks
- Unauthorized access
- SQL injection
- Cross-site scripting (XSS)
- DNS hijacking
- Malware infection

## Social Engineering
- All techniques aimed at talking a target into revealing specific information or performing a specific action for illegitimate reasons.
- Either by using psychological manipulation to get further access to an IT system where the actual objective of the scammer resides, e.g. impersonating an important client via a phone call to lure the target into browsing a malicious website to infect the target's workstation;
- Or using IT technologies as support to psychological manipulation techniques to achieve an objective outside the IT realm, e.g. obtaining banking credentials via a phishing attack to then steal the target's money.
- The increasing use of IT technologies has naturally led to an increase in the use of such techniques, as well as to their combination, to such a point that most cyber attacks nowadays include some form of social engineering.

## HTML Injection
- Client-side rendering without sanitization and the HTML was injected into the page.
- Hypertext Markup Language (HTML) injection is a technique used to take advantage of non-validated input to modify a web page presented by a web application to its users.
- Attackers take advantage of the fact that the content of a web page is often related to a previous interaction with users.
- When applications fail to validate user data, an attacker can send HTML-fomatted text to modify site content that gets presented to other users.
- A specifically crafted query can lead to inclusion in the web page of attacker-controlled HTML elements which change the way the application content gets exposed to the web.

- Your web app template:
```
 <html>
    <h1>Recent users queries:</h1>
    <ol>
         <li><h2>{user-query-1}</h2> 
   </ol>
</html>
```

- With HTML Injection
```
<html>
    <h1>Recent users queries:</h1>
    <ol>
         <li><h2></h2>special offer <a href=www.attacker.site>malicious link</a><h2></h2>
   </ol>
</html>
 ```
