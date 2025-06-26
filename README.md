# NodeGoat-Security-Internship
This is a Cybersecurity internship project focused on analyzing and strengthening a vulnerable web-based User Management System using OWASP NodeGoat. Tasks include vulnerability assessment, implementing security measures (XSS, SQLi, password hashing, JWT, Helmet), logging, and final reporting.

Cybersecurity Internship Project – Securing OWASP NodeGoat
            Welcome to my Cybersecurity Internship Project. Over three weeks, I explored and secured a vulnerable web application - OWASP NodeGoat - by identifying real-world security flaws and applying best practices to fix them.This project includes the working code with security improvements, documentation, and logs based on the internship requirements.

● Project Overview
 The goal of this internship was to:
   Understand and set up a mock web application (NodeGoat)
   Identify vulnerabilities using automated tools and manual techniques.
   Apply secure coding practices, including input validation, password hashing, JWT-based authentication, and security headers.
   Conduct penetration testing and logging.
   Submit findings and fixes in a documented format.

● Tools and Technologies Used

1-Application:
   ● Node.js
   ● Express.js
   ● MongoDB

2-Security Tools:
   ● OWASP ZAP (automated vulnerability scanning)
   ● Browser Developer Tools (manual testing)
   ● Nmap (network scanning)

3-Security Libraries:
   ● validator
   ● bcrypt
   ● jsonwebtoken
   ● helmet
   ● winston

Weekly Breakdown

● Week 1: Vulnerability Assessment
 Tasks Performed:
  Cloned and ran OWASP NodeGoat application.
  Explored web pages: /signup, /login, /profile.
  Performed vulnerability testing using:
     ● OWASP ZAP (automated scans)
     ● Browser Developer Tools (manual XSS tests)
     ● SQL Injection tests (using admin' OR '1'='1)

Vulnerabilities Identified:
  ●  Cross-Site Scripting (XSS)
  ●  SQL Injection
  ●  Plaintext password storage
  ●  Missing security headers
  ●  No token-based authentication

● Week 2: Implementing Security Measures
Tasks Performed:
Input Validation and Sanitization:
Installed validator library.
Added checks to validate email format and sanitize inputs.
Example:
const validator = require('validator');
if (!validator.isEmail(email)) {
return res.status(400).send('Invalid email');
}
Password Hashing:
Installed bcrypt.
Replaced plaintext password storage with bcrypt hashing.
Example:
const bcrypt = require('bcrypt');
const hashedPassword = await bcrypt.hash(password, 10);

JWT Authentication:
Installed jsonwebtoken.
Added login token generation for secure access.
Example:
const jwt = require('jsonwebtoken');
const token = jwt.sign({ id: user._id }, 'your-secret-key');
res.send({ token });

Secure Headers with Helmet:
Installed and used helmet to set secure HTTP headers.
Example:
const helmet = require('helmet');
app.use(helmet());

● Week 3: Advanced Security and Finalization
Tasks Performed:
Basic Penetration Testing:
Simulated common attacks using browser tools.
Scanned ports using Nmap.
Logging with Winston.
Installed winston.
Set up logging to both console and file (security.log).
Example:
const winston = require('winston');
const logger = winston.createLogger({
transports: [
new winston.transports.Console(),
new winston.transports.File({ filename: 'security.log' ]})
]
});
logger.info('Application started');

Final Documentation :
● Created final report listing vulnerabilities and fixes.
● Final Security Checklist
● Input validation on all fields
● Sanitized data before database entry
● Hashed passwords using bcrypt
● Token-based authentication using JWT
● Helmet used for securing HTTP headers
● Logging implemented using Winston
● Basic testing with OWASP ZAP and Nmap

Key Learnings
● Real-world web application vulnerabilities and how to identify them
● Secure coding best practices in Node.js
● Using OWASP ZAP for automated testing
● Implementing JWT, bcrypt, and helmet for strong application security
● Logging user actions and system events for better traceability

How to Set Up Locally
1- Clone the repository:
  git clone https://github.com/your-username/NodeGoat.git
2- Navigate into the directory:
  cd NodeGoat
3- Install dependencies:
  npm install
4- Run the server:
  npm start
5-Access the application in the browser:
  http://localhost:4000

Report Summary
   A full report describing each vulnerability, test performed, fix applied, and final testing results with screenshots is included in this repository.
