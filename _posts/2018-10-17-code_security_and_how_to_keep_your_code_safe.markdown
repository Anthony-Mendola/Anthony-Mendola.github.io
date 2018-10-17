---
layout: post
title:      "Code Security and How to Keep your Code Safe"
date:       2018-10-17 16:19:47 +0000
permalink:  code_security_and_how_to_keep_your_code_safe
---


A recent analysis of over 133,000 websites has found that 37% of them have at least one JavaScript library with a known vulnerability. 

Hackers use flaws in dependencies to exploit and steal your data. 

### How do we protect ourselves?

The easiest way is to always ensure that your dependencies are up to date. With so many projects, this can be a daunting task. My favorite solution is Snyk.

![](https://i.imgur.com/CDC1GGx.jpg?1)

Snyk is really easy to use. Just sign up, connect your github, and add the repos you want scanned. Snyk will scan through your repo on a scheduled basis to ensure there are no vulnerabilities. You'll even get email notifications as soon as something pops up.

![](https://i.imgur.com/XGwbv1e.jpg?1)

On your dashboard you'll have a current security status of all your scanned projects.

![](https://i.imgur.com/Zqsjsvl.jpg?1)


And the best part....it's open source and **FREE**

Link for free signup [https://app.snyk.io/signup](http://)

For further information on this subject I highly recommend watching this video on JavaScript flaws and how hackers abuse them:

<iframe width="560" height="315" src="https://www.youtube.com/embed/0dgmeTy7X3I" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>



