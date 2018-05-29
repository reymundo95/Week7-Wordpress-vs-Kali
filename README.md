# Week7-Wordpress-vs-Kali
Time spent: 5 hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. Cross Site Scripting (XSS)
  - [x] Summary: A XSS vulnerability revealed that the webpage was able to be injected with malicious java code and can create an instance where a user can simply hover their mouse over the infected site.  This causing the victim of who ever is on the webpage to simply hover their mouse over the intended target and cause damage.
    - Vulnerability types: subject to XSS
    - Tested in version: 4.2
  - [x] GIF Walkthrough: <a href="https://imgur.com/OfITuEL"><img src="https://i.imgur.com/OfITuEL.gif" title="source: imgur.com" /></a>
  - [x] Steps to recreate:
 
        
         1. Initialized a place to put injected XSS code into header of page 
         2. Chose a xss code that involved being initiated once you hover mouse over the title
         3. Place XSS code into the heading of the page.
         4. Update the page with the XSS in the in the heading.
         5. View the permalink of the page
         6. Simply hover the mouse over the heading of the page.
         7. XSS alert message appears 
         
2. Privelage Escalation 
  - [x] Summary: the comment section had a privelage escalation where a user, that is not admin, can simply submit a comment. since every comment has to be approved by the admin. But as soon as that comment is approved then the user is able to submit as many comments without having their comments approved. 
    - Vulnerability types:  
    - Tested in version: 4.2
  - [x] GIF Walkthrough: 
    <a href="https://imgur.com/KiIIFg5"><img src="https://i.imgur.com/KiIIFg5.gif" title="source: imgur.com" /></a>
    
    Longer gif link click here:
    <a href="https://imgur.com/n5QegtJ"><img src="https://i.imgur.com/n5QegtJ.gif" title="source: imgur.com" /></a>
  
  - [x] Steps to recreate: 
  
         1. Create a new user
         2. Give New user a role (subscriber)
         3. Create a page (IST590)
         4. Login into the new user through a incongnito window
         5. As the new user simply head over to the page (IST590)
         6. Place a commment and press submit.
         7. Comment should say "comment waiting for moderation" meaning it needs approval to post into site.
         8. Switch windows back into the admin page, refresh page.
         9. Approve last comment posted
         10. switch back to subscriber in incognito mode windows
         11. Post another comment
         12. Will not need to wait for approval
         
    
3. IDOR
  - [x] Summary: The vulnerability of this is where the site can expose information if there is a modification of the url by providing the statement"readme.html towards the end of the URL. Thus redirecting the page to a page where the site should not have led to.
    - Vulnerability types: Readme.html vulnerability
    - Tested in version: 4.2
  - [x] GIF Walkthrough: <a href="https://imgur.com/HKrEgBd"><img src="https://i.imgur.com/HKrEgBd.gif" title="source: imgur.com" /></a>
  - [x] Steps to recreate: 
  
          1. Identified that there was a vulnerability by changing the URL
          2. erase everything after wpdistillery.vm/"xxxxxxx"
          3.replace the text that you erased with "readme.html"
          4. Press enter
          5. Web page reveals information regarding system requirement, final notes
 

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Challenges that was encountered through my work was mainly due to setting up the lab environment. Everytime the lab environment was getting prepared for, it will give an error message relating to the vagrant setup in my host machine. Later once envireonment was finally set up, it would work fine. But once the host computer was shut off and turned on the environment would not work upon turning on. Would have to keep unistalling and reinstalling vagrant and starting from scratch.

## License

    Copyright [2018] [Reymundo Reza]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
