# Project 8 - Pentesting Live Targets

Time spent: **X** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:
* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each version of the site has been given two of the six vulnerabilities. (In other words, all six of the exploits should be assignable to one of the sites.)

## Blue

Vulnerability #1: SQL Injection (SQLi)

Attempting to inject a database query at the end of the URL of a salesperon page with ```'OR 1'--``` causes the database query to fail. This error shows the endless possibilites of potential SQLi. Red and Green properly reroute you when attempting this there.

<img src='sqlinjection.gif' title='SQLi' width='' />

Vulnerability #2: Session Hijacking/Fixation

Log into your account and add ```/hacktools/change_session_id.php``` to the end of the url. You are able to copy your current session id. On a different browser or private/incognito varient of your current browser, access ```https://35.184.88.145/blue/public/hacktools/change_session_id.php``` and paste the session id obtained from the logged in user and click "Change." Now when you access ```https://35.184.88.145/blue/public/``` and click "Login" on your different/private browser, you are logged in without ever logging in!

<img src='sessionhijacking.gif' title='SesHijack' width='' />

## Green

Vulnerability #1: Cross-Site Scripting (XSS)

Press the "Contact" button and start filling out the information. In the Feedback area, type ```<script>alert('Luis found the XSS!');</script>```. Now login and view the "Feedback." An alert will come up on the screen with what you entered before.

<img src='crosssitescripting.gif' title='xss' width='' />

Vulnerability #2: Username Enumeration

When attempting to login as someone who exists in the system like "jmonroe99," the "Log in was unsuccessful" text will be bold. Now when trying to login as someone who doesn't exist, the "Log in was unsuccessful" text will not be bold. This reveals who has an actual account on the website.

<img src='userenumeration.gif' title='ue' width='' />

## Red

Vulnerability #1: __________________

Vulnerability #2: __________________


## Notes

Describe any challenges encountered while doing the work
