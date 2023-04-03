## XSS 

- XSS lands at the top 10 on the OWASP top 10.
- An XSS attack occurs when malicious scripts are injected into an application usually through a web request.
- There are three basics types of XSS
    - Reflected
    - Stored
    - DOM

## Reflected XSS

Reflected XSS occurs when an injected script is reflected somewhere in the application. The reflection can be in an error, the HTML code, a search box, or a form.

If XSS is found, an attacker will create a website or craft an email that contains the legitimate website but the reflection points to the attacker's controlled site.

When the victim clicks on the link or loads the email, the XSS will fire and any session cookies that the victim has will be printed to the attackers site. The attacker can then use the session to log in as the victim.

## Stored XSS

This type of XSS is considered to have more of an impact than reflected XSS. As the name states, the payload is permanently stored on the web server. The user is not required to open an email or visit a malicios site. Instead, visiting the legitimate site is enough to fire the payload.

According to OWASP, HTML5-stored XSS attacks can now be permanently stored in a victims browser and not need the web server for the attacker to collect data.

As technloogies chance, so does the attack.


## DOM (Document Object Model)

When a web page is loaded, the browser creates a document object model of the page.

DOM is an API that allows HTML elements to be modified.

DOM occurs when when an attacker can inject a script into the DOM. Its a client side attack. Thus, the attack never reaches the web server. This makes it difficult to discover and forensically investigate.

Essentially a firewall will not help against such an attack. The best mitgation is to carefully analyze the code and attempt injections while in development and production.

## Code Sanitization/Escaping

TO remove any unwanted or ilegal characters that could be used to maliciously attack the page/site.

An example would be script thats `<>`

