# Enigma Group Project #1

## Student Information

* Student name: Michael Cox
* NetId: mcox59
* Enigma group profile: <https://www.enigmagroup.org/profile/66960>


## Project Description

In this project, you will be complete the following challenges on [Enigma Group](https://www.enigmagroup.org/pages/challenges): Basic 1–3 (starter) and 4–8 (JavaScript). After completing each challenge you will complete the following worksheet describing:
1. The credentials found in the challenge (if any).
2. How you solved the challenge. Include any JavaScript or other scripts you used to solve these challenges. 
3. What sins (as found in the *24 Deadly Sins* book) are evidenced in the challenge.
4. How those sins should be addressed to address your exploit.

You can find a basic guide for markdown formatting [here](https://www.markdownguide.org/basic-syntax/). In particular, note the [code section](https://www.markdownguide.org/basic-syntax/#code) which should be used to annotate any code or commands used in your writeup.


## Challenges

---
### Basic 1

#### Credentials
39f13b

#### How you found the credentials
The password is stored in a comment in the source html. One can use chrome's 'Inspect Element' to view the commented password.

#### What sins are evidenced in this challenge
[CWE-312: Cleartext Storage of Sensitive Information](https://cwe.mitre.org/data/definitions/312.html)
[CWE-319: Cleartext Transmission of Sensitive Information](https://cwe.mitre.org/data/definitions/319.html)
[CWE-615: Inclusion of Sensitive Information in Source Code](https://cwe.mitre.org/data/definitions/615.html)

#### How could those sins be mitigated
1. Remove the password from the source.
2. Securely hash passwords.
3. Use HTTPS.



---
### Basic 2

#### Credentials
`admin:rosebud101z`

#### How you found the credentials
1. An "error message" reveals that there is a file that failed to load at `dontlookinhere/password.inc`
2. `dontlookinhere` is indexable, revealing that there is a file `password.inc`.
3. `password.inc` contains the cleartext credentials.

#### What sins are evidenced in this challenge
[CWE-209: Generation of Error Message Containing Sensitive Information](https://cwe.mitre.org/data/definitions/209.html)
[CWE-313: Cleartext Storage in a File or on Disk](https://cwe.mitre.org/data/definitions/313.html)
[CWE-319: Cleartext Transmission of Sensitive Information](https://cwe.mitre.org/data/definitions/319.html)
[CWE-548: Exposure of Information Through Directory Listing](https://cwe.mitre.org/data/definitions/548.html)

#### How could those sins be mitigated
1. Securely hash passwords.
2. Remove world read permissions from files containing sensitive information.
3. Reconfigure the web server to hide directory listings.
4. Remove sensitive information from error messages.
5. Use HTTPS.



---
### Basic 3

#### Credentials
```
$username = "admin";
$password = "f0rkblork";
```

#### How you found the credentials
1. A standard `robots.txt` file exposes the directory `/f0rk`.
2. `/f0rk` is indexable, revealing a file `/f0rk/confic.inc`
3. `config.inc` contains the credentials in cleartext.

#### What sins are evidenced in this challenge
[CWE-200: Exposure of Sensitive Information to an Unauthorized Actor](https://cwe.mitre.org/data/definitions/200.html)
[CWE-313: Cleartext Storage in a File or on Disk](https://cwe.mitre.org/data/definitions/313.html)
[CWE-319: Cleartext Transmission of Sensitive Information](https://cwe.mitre.org/data/definitions/319.html)
[CWE-548: Exposure of Information Through Directory Listing](https://cwe.mitre.org/data/definitions/548.html)

#### How could those sins be mitigated
1. Securely hash passwords.
2. Remove world read permissions from files containing sensitive information.
2. Remove sensitive information from `robots.txt`, or remove `robots.txt` entirely.
3. Reconfigure the web server to hide directory listings.
4. Use HTTPS.



--- 
### Basic 4

#### Credentials
N/A.

#### How you passed the challenge
1. Use Chrome's Inspect Element tool to change one of the Select form's options to "Jane".

#### What sins are evidenced in this challenge
[CWE-200: Exposure of Sensitive Information to an Unauthorized Actor](https://cwe.mitre.org/data/definitions/200.html)
[CWE-287: Improper Authentication](https://cwe.mitre.org/data/definitions/287.html)
[CWE-319: Cleartext Transmission of Sensitive Information](https://cwe.mitre.org/data/definitions/319.html)
[CWE-656: Reliance on Security Through Obscurity](https://cwe.mitre.org/data/definitions/656.html)

#### How could those sins be mitigated
1. Remove hint of correct username.
2. Enforce authentication with some information only authenticated users can know.
3. Use HTTPS.



---
### Basic 5

#### Credentials
`skriptkid`

#### How you found the credentials
1. Open Developer Tools and go to the Network tab in Chrome.
2. Load the website and view the network response in `2/`.
3. Notice the password is hard-coded in the client-side javascript.
4. Notice that the authentication success redirects to `skriptkid.php`.

#### What sins are evidenced in this challenge
[CWE-259: Use of Hard-coded Password](https://cwe.mitre.org/data/definitions/259.html)
[CWE-319: Cleartext Transmission of Sensitive Information](https://cwe.mitre.org/data/definitions/319.html)
[CWE-602: Client-Side Enforcement of Server-Side Security](https://cwe.mitre.org/data/definitions/602.html)
[CWE-615: Inclusion of Sensitive Information in Source Code](https://cwe.mitre.org/data/definitions/615.html)

#### How could those sins be mitigated
1. Enforce password authentication on the server.
2. Do not hard code passwords.
3. Securely hash passwords.
4. Use HTTPS.
5. Do not include passwords in public filenames.



---
### Basic 6

#### Credentials
`Sauc3`

#### How you found the credentials
1. Open Developer Tools and go to the Network tab in Chrome.
2. Load the website and view the network response in `3/`.
3. Notice the password is hard-coded in the client-side javascript.
4. Notice that the authentication success redirects to `Sauc3.php`.

#### What sins are evidenced in this challenge
[CWE-259: Use of Hard-coded Password](https://cwe.mitre.org/data/definitions/259.html)
[CWE-319: Cleartext Transmission of Sensitive Information](https://cwe.mitre.org/data/definitions/319.html)
[CWE-602: Client-Side Enforcement of Server-Side Security](https://cwe.mitre.org/data/definitions/602.html)
[CWE-615: Inclusion of Sensitive Information in Source Code](https://cwe.mitre.org/data/definitions/615.html)
[CWE-656: Reliance on Security Through Obscurity](https://cwe.mitre.org/data/definitions/656.html)

#### How could those sins be mitigated
1. Enforce password authentication on the server.
2. Do not hard code passwords.
3. Securely hash passwords.
4. Use HTTPS.
5. Do not include passwords in public filenames.
6. Do not rely on obscurity to hide passwords.



---
### Basic 7

#### Credentials
`shifted`

#### How you found the credentials
1. Open Developer Tools and go to the Network tab in Chrome.
2. Check "Preserve log".
3. Load the website and view the network response in `index.php`.
4. Notice the password is hard-coded in the client-side javascript.
5. Notice that the authentication success redirects to `shifted.php`.

#### What sins are evidenced in this challenge
[CWE-259: Use of Hard-coded Password](https://cwe.mitre.org/data/definitions/259.html)
[CWE-319: Cleartext Transmission of Sensitive Information](https://cwe.mitre.org/data/definitions/319.html)
[CWE-602: Client-Side Enforcement of Server-Side Security](https://cwe.mitre.org/data/definitions/602.html)
[CWE-615: Inclusion of Sensitive Information in Source Code](https://cwe.mitre.org/data/definitions/615.html)

#### How could those sins be mitigated
1. Enforce password authentication on the server.
2. Do not hard code passwords.
3. Securely hash passwords.
4. Use HTTPS.
5. Do not include passwords in public filenames.



---
### Basic 8

#### Credentials
`ASCII-Chart`

#### How you found the credentials
1. Open Developer Tools and go to the Network tab in Chrome.
2. Check "Preserve log".
3. Load the website and view the network response in `index.php`.
4. Notice the password is hard-coded as an escaped string in the client-side javascript.
5. Unescape the password using javascript `unescape()`
6. Notice that the authentication success redirects to `ASCII-Chart.php`.

#### What sins are evidenced in this challenge
[CWE-259: Use of Hard-coded Password](https://cwe.mitre.org/data/definitions/259.html)
[CWE-319: Cleartext Transmission of Sensitive Information](https://cwe.mitre.org/data/definitions/319.html)
[CWE-602: Client-Side Enforcement of Server-Side Security](https://cwe.mitre.org/data/definitions/602.html)
[CWE-615: Inclusion of Sensitive Information in Source Code](https://cwe.mitre.org/data/definitions/615.html)

#### How could those sins be mitigated
1. Enforce password authentication on the server.
2. Do not hard code passwords.
3. Securely hash passwords.
4. Use HTTPS.
5. Do not include passwords in public filenames.


