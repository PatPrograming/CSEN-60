# Web Security and Privacy

## Security

### Potential Security Oversights
- No user authentication
- Allowing weak authentication
- Not sanitizing form entries and requests
- Not encrypting sensitve communications
- Sessions that don't time out
- Out of date (unpatched) software
    - New vulnerabilities discovered all the time
- Bugs that expose user data

### Cross Site Scripting
- The attacker inserts arbitrary HTML on your webpage
    - How can this ever happen?
- What can go wrong
    - Change content of the page
    - Steal user's information

- What if the HTML includes script tags?
    - Replace the page with a new one
        - Fake instance of a page to get passwords, accounts, etc.
    - Pass information from the page to foreign page
        - Cookies, passwords, credit card numbers, session ids
    - Download user's cookies (passwords) for other sites

### Cross Site Scripting: How
Request:

Get/welcome.php?name=Robbie%20Culkin
Host: www.vulnerable.site

Response:

![Response for Cross Site Scripting](ResponseCrossSiteScripting.png)

![Response for Cross Site Scripting](ResponseCrossSiteScripting2.png)

### Cross Site Scripting: Mitgation 
- Don't allow any HTML to be inserted
    - Backend libraries to strip out HTML tags
- Don't allow malicious HTML to be inserted
    -  Backend libraries to scirpt out the HTML tags
        - Limited set of allowed tags for formatting
- Similar techniques  may be used to protect against SQL inject

### Distributed Denial of Service
- DDos
- Overwhelm a server with malicious requests to block regular users
- Requests don't come from one machine
    - These are easily blocked
- Attackers use a number of controlled machines, often comprised
    - Hard to spot

### DDos Mitigation
- Rate limiting
    - Limit volume of requests from a user
- Throw out excess traffic at random
    - Some will be malicious, some will be legitimate
- Distribute traffic across network
    - By distributing load, can accommodate huge volume

### Netowrk Security
- Need to send requests: GET/POST
- Need to send responses: HTML Documents
- Network channels aren't necessarily secure
- Confidentiality: What if someone intercepts and reads this message?
- Integrity: What if someone intercepts and alters this message?

### Secure Communication
- For anyone other than the intended recipient,  we want our messages to be:
    - Unreadable
    - Impossible to change without detection
- Encryption function
    - F(X) = Y easy to compute
    - F^-1(Y) = X difficult to compute (without additional knowledge)

### Encryption and Decryption

- Encryption
    – Ensures privacy within an organization and on the Internet
    – The conversion of data into an unreadable form called ciphertext

- Decryption
    – The process of converting the ciphertext back into its original form, called plaintext or cleartext, so it can be understood.
    - The encryption/decryption process requires an algorithm and a key.

## Privacy 
### Privacy Policy

- Statement saying what the web site does with any information it collects
- Or otherwise obtains from the user
- And why the web site needs this information
    - Generally considered legally binding
- Must obey the laws of the land
- Different lands have different laws
    - Written in dense legal language
    - Users may or may not pay attention

### The Role of a Privacy Policy

- Delineate what types of information are collected
- Whether that information is used immediately or
saved

- Specify why the information is needed
- Not always done
- Useful if the application is not obvious
- Specify who owns the information
- If you own your information, company can’t use it freely
- If they own the information things are more flexible

### Specify what an application can do with the information
- Use in the application only
- Use in the application and the owning company
- Use in the application, owning company, affiliates
- Share (sell to) with related businesses
- Share (sell to) with anyone
    - Specify which controls you have over the information
- Can you stop it from being collected
- Can you request any collected information be discarded

### Digital Certificate
- Form an asymmetric key
- Also contains information about the certificate, the holder of the certificate, and the issuer of the certificate.
- Used by SSL (Secure Socket Layer) to auth the identify of the web server

- Contents of a server's digital certificate include:
    - The public key
    - Effective date of the certificate
    - Expiration date of the certificate
    - Details about the certificate authority: issuer of the certificate
    - Details about the certificate holder
    - A digest of the certificate context

### Cerficate Authority
- Trusted third party org which certifies a web server with a digital certificate

- Well known
    - IdenTrust
    - DigiCert
    - GTS

### Data Collection
- Social Networks
- Online Shopping
- Online finances

### Mobile OS-provided
- Contacts
- Photos
- Location

### Cookies
- A cookie is a name value pair created by a website to store information on your computer
- Why?
    - user Auth
    - Site preferences
    - Contents of shopping carts

### Behavior Logging
- Any action a user takes on a webpage can be logged
- HTML event listeners!
    - Clicks
    - Hovers
- Time between actions
    - How long you spend looking at a post
    - Did you skip an ad? At what point in the ad?

### Data Applications: Ad Tracking
- How are all these porducts free?
    - Facebook/Twitter/LinkedIn
    - Google
    - YouTube / Soundcloud
- Goal: convert an ad seen on screen to some action
- The better targeted the ad, the better chance of a conversion ($$$)

### Drive a metric
- Optimize a webpage's behavior for something that can be quantitatively measured 
- Iterative UI imporvements
- A/B Testing

### Lots osf Sensitive Information
- Personally identifiable information - PII
- Financial information
- Legally sensitive
    - HIPPS Health
    - FERPA Students
    - COPPA Kids

### Privacy Policy
- Statment saying what the web site does with any information it collects

### Developer - Legal Responsibility
- Privacy has legal implications
    - European law is generally much stricter than US
    - China has policy of censorship
- Developer is responsible for breaches of policy

### GDPR
- General Data protection Regulation
- Protects citizens of the European Union
- Users must provide consent
- Must collect minimum amount of data to acheive stated purpose
- Consumers may view data

### CCPA
- California Consumer Privacy Act
- Similar to, less strict that GDPR
    - Opt-out vs. Consent
    - "Do not sell my personal data"