# SWAT
## Error Handling and Logging
- Display generic error message (CWE-209)
- No Unhandled Exceptions (CWE-3
- Surpress Framework Generated Errors (CWE-209)
- Log all authentication and validation activities (CWE-778)
- Log all privilege changes (CWE-778)
- Log access to sensitive data (CWE-778)
- Do no log sensitive data (CWE-532)
- Store logs securely (CWE-533)

## Data Protection
- Use HTTPS Everywhere (CWE-311/319/523)
- Disable HTTP access for all protected resources (CWE-319)
- Use strict-transport-security (STS) headers
- Store user passwords using a strong, iterative, salted hash (CWE-257)
  - Use mulitple rounds of a strong hash function such as pbkf2 and bcrypt
- Securely exchange encryption keys
- Setup a secure key management process (CWE-320)
  - Use a key vault to allow central key location with ease of rotation
- Use strong TLS configurations
- Use valid TLS certificate from reputable CA
- Disable data caching using cache control headers and autocomplete (CWE-524)
  - Set these headers to prevent the browser from storing sensitive data locally
- Encrypt sensitive data at rest (CWE-311/312)

## Authenication
- Don't hardcode credentials (CWE-798)
- Develop a strong password reset system (CWE-640)
  - Questions need to be both hard to guess and hard to brute force. Consider 2FA.
- Implement a strong password policy (CWE-521)
- Implement account lockout against brute force attacks (CWE-307)
- Don't disclose too much information in error messages (invalid credntials)
- Store database credentials securely (CWE-257)
- Applications and middleware should run with minimal privileges (CWE-250)

## Session Management
- Ensure session identifier are sufficently random (CWE-6)
- Regenerate session tokens (CWE-384)
  - Should be changed on authentication, and when user privilege level changes
- Implement idle session timeout (CWE-613)
- Implement absolute session timeout (CWE-613)
- Destory sessions as any sign to tampering
  - detect session cloning attemps and other anomoly detection which will invalidate the session
- Invalidate the session after logout (CWE-613)
- Place a logout button on every page
- Use secure cookie attributes (CWE-79/614)
  - HttpOnly, Secure
- Set the cookie domain and path correctly
  - Set domain and path to be the most restrictive for the application
- Set the cookie expiration time

## Input and Output Handling
- Conduct contextual output encoding (CWE-79)
  - Encode for the destination output location (HTML page, URL, etc)
- Prefer whitelist to blacklists (CWE-159/144)
- Use parameterized SQL queries (CWE-89/564)
- Set the encoding for your application (CWE-172)
  - Set default encoding using HTTP headers for the application
- Validate uploaded files (CWE-434/616/22)
- Use the nosniff header for uploaded content to prevent MIME Sniffing (CWE-430)
  - Will prevent browser from attempting to render the content
- Prevent Tabnabbing
  - Add rel=”noopener noreferrer” to prevent changing to the openned tab
- Validate the source of input (CWE-20/346)
  - If expected request type is a POST, only except POSTs
- X-Frame-Options or CSP headers (CWE-693)
  - Use X-Frame-Options or Content-Security-Policy to prevent foreign content from being loaded on the page
- Use secure HTTP response headers
  - use Content-Security-Policy, X-XSS-Protection and Public-Key-Pins headers to secure responses
  
## Configuration and Operations
- Automate application deployment
  - Use CI/CD to deploy changes to production repeatably
- Establish a rigorous change management process (CWE-439)
- Define security requirements
- Conduct design review (CWE-701/656)
- Conduct a code review (CWE-702)
- Perform security testing
- Harden the infrastructure (CWE-15/656)
- Define an incident handling plan
- Educate the team on security

## Access Control
- Apply access control checks consistently (CWE-284)
  - Force all requests through a common security gatekeeper
- Apply the principal of least privilege (CWE-272/250)
- Don't sure direct object references for access control checks (CWE-284)
- Don't use unvalildated forwards or redirects (CWE-601)
  - Can allow access to private data
 
