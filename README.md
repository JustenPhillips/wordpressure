# Project 7 - WordPress Pentesting

Time spent: 10 hours spent in total

> Objective: Find, analyze, recreate, and document 3/5 affecting an old version of WordPress

## Pentesting Report

1. (Required) WordPress 3.7-4.4.1 - Open Redirect
  - [x] Summary: spoof a login page to harvest credentials or redirect to another malicious site
    - Vulnerability types: HTTPS Redirect
    - Tested in version: 4.1
    - Fixed in version: 4.2.7
  - [x] GIF Walkthrough: <br>
      <img src='https://media.giphy.com/media/YV3bdO6JoBD0ZbmUhF/giphy.gif'/>
  - [x] Steps to recreate: 
      1.log in then log out
      2.add the ?redirect_to=anywebpage to the URL in the address bar
      3.when they sign in they will be redirected to the page
      -P.o.C:
  wpdistillery.vm/wp-login.php?redirect_to=http://maliciousscript.hax
  - [x] Affected source code:
    - https://core.trac.wordpress.org/changeset/36444

2. (Required) WordPress <= 4.3 - Authenticated Shortcode Tags Cross-Site Scripting (XSS)
  - [x] Summary: The following payload placed in a page or post (does not work in comments)
    - Vulnerability type: Stored XSS
    - CVE 2015-5714
    - Tested in version: 4.1
    - Fixed in version: 4.2.5
    - P.O.C: TEST!!![caption width="1" caption='<a href="' ">]</a><a href="http://onMouseOver='alert(1)'">Click me</a>
  - [x] GIF Walkthrough: <br>
    <img src='https://media.giphy.com/media/1i4Smx9u77YyEAKc7q/giphy.gif'/>
  - [x] Steps to recreate: 
    -add a new post, not a comment
    -inject a tag in the html that 
  - [x] Affected source code:
    - https://github.com/WordPress/WordPress/commit/f72b21af23da6b6d54208e5c1d65ececdaa109c8
    
 3. (Required) WordPress <= 4.9.4 - Application Denial of Service (DoS)
  - [x] Summary: 
    - Vulnerability types: Denial of Service attack
    - Tested in version: 4.1
    - Fixed in version: 4.9.2
  - [x] GIF Walkthrough: 
    <br>
    <img src='https://media.giphy.com/media/4WF55RRHEDoSicH0ES/giphy.gif'/>
  - [x] Steps to recreate: 
  A simple Script In Python With threading,the flaw affects the load-scripts.php WordPress script, it receives a parameter called load[]
  - [x] Affected source code: unpatched
    -https://github.com/WazeHell/CVE-2018-6389/blob/master/CVE-2018-6389.py

4. (optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
## Assets

List any additional assets, such as scripts or files

## Resources
- https://wpvulndb.com/(https://wpvulndb.com/vulnerabilities/8186)
- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).
uploaded with https://giphy.com
## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
