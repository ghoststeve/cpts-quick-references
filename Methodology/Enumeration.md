## Network Service Enumeration Checklist

### General Network Enumeration
- [ ] Identify all live hosts on the network
- [ ] List open ports for each host
- [ ] Determine operating systems of targets
- [ ] Map network topology
- [ ] Identify firewalls and security appliances
- [ ] Identify credentials
- [ ] Test found credentials on other services

### DNS (Port 53)
- [ ] Attempt zone transfers
- [ ] Check for wildcard DNS
- [ ] Enumerate subdomains
- [ ] Look for internal IP addresses in DNS records
- [ ] Check for DNS cache snooping

### FTP (Port 21)
- [ ] Check for anonymous access
- [ ] List accessible directories and files
- [ ] Attempt to upload and download files
- [ ] Check for outdated FTP server versions

### SSH (Port 22)
- [ ] Identify SSH version
- [ ] Check for weak ciphers and key exchange methods
- [ ] Test for user enumeration timing attacks
- [ ] Look for custom banners with sensitive information

### SMTP (Port 25)
- [ ] Verify SMTP commands (VRFY, EXPN, RCPT TO)
- [ ] Enumerate valid email addresses
- [ ] Check for open relay configuration
- [ ] Identify mail server software and version

### HTTP/HTTPS (Ports 80/443)
    Basic Enumeration Checklist
- [ ] Identify web server and version
- [ ] Check for HTTP methods allowed (OPTIONS)
- [ ] Look for default pages and directories
- [ ] Analyze SSL/TLS configuration
- [ ] Check for virtual hosts

Web Application Enumeration Checklist

### SMB (Port 445)
- [ ] List shared folders
- [ ] Check for null sessions
- [ ] Enumerate users and groups
- [ ] Identify SMB version
- [ ] Look for known SMB vulnerabilities based on version

### SNMP (Port 161)
- [ ] Try default community strings
- [ ] Enumerate system information (hostname, domain, users)
- [ ] List running processes and installed software
- [ ] Check for writable SNMP OIDs

### Database Ports (e.g., 1433 for MSSQL, 3306 for MySQL)
- [ ] Identify database type and version
- [ ] Check for default credentials
- [ ] Enumerate database names
- [ ] Look for exposed management interfaces

### NFS (Port 2049)
### IMAP/POP3 (Port 143/993)
### Oracle TNS (Port 1521)
### IPMI (Port 623)

## Web Application Enumeration Checklist

### Initial Reconnaissance
- [ ] Identify web server type and version
- [ ] Detect web application framework
- [ ] Check robots.txt and sitemap.xml
- [ ] Review source code of main pages
- [ ] Identify all entry points (forms, parameters, APIs)

### Directory and File Enumeration
- [ ] Discover hidden directories
- [ ] Look for backup files (.bak, .old, .copy)
- [ ] Check for exposed configuration files
- [ ] Identify admin or management consoles
- [ ] Look for version control files (.git, .svn)

### Authentication Mechanisms
- [ ] Test for user enumeration
- [ ] Check password complexity requirements
- [ ] Look for password reset functionality
- [ ] Test for brute force protection
- [ ] Check for multi-factor authentication options

### Session Management
- [ ] Analyze session token generation
- [ ] Check session timeout implementation
- [ ] Test for session fixation
- [ ] Verify secure flag on cookies
- [ ] Look for exposed session IDs in URLs

### Input Validation
- [ ] Test all input fields for XSS
- [ ] Check for SQL injection points
- [ ] Test for command injection
- [ ] Look for IDOR (Insecure Direct Object References)
- [ ] Check file upload functionality

### Information Disclosure
- [ ] Examine error messages
- [ ] Look for comments in source code
- [ ] Check HTTP headers for sensitive information
- [ ] Test for user enumeration in responses
- [ ] Look for exposed internal IPs or hostnames

### Application Logic
- [ ] Map out the application's functionality
- [ ] Identify the role and permission system
- [ ] Look for race conditions
- [ ] Test business logic for flaws
- [ ] Check for insecure direct object references

### API Enumeration
- [ ] Identify API endpoints
- [ ] Determine API authentication methods
- [ ] Look for API documentation
- [ ] Test for excessive data exposure
- [ ] Check for rate limiting

### Third-party Components
- [ ] Identify third-party libraries and versions
- [ ] Check for known vulnerabilities in components
- [ ] Look for default configurations in plugins
- [ ] Test for security misconfigurations in integrations

### Client-side Controls
- [ ] Analyze JavaScript for sensitive information
- [ ] Look for client-side validation only controls
- [ ] Check for exposed API keys or credentials
- [ ] Test for DOM-based vulnerabilities

Remember to document all findings thoroughly as you go through these checklists. The goal is to build a comprehensive understanding of the target environment, which will inform your vulnerability analysis and exploitation attempts in later stages of the penetration test.
