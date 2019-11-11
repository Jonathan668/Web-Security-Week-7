# Project 7 - WordPress Pentesting

Time spent: **9** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

**1. (Required) Vulnerability Name or ID: Authenticated Stored Cross-Site Scripting (XSS)**
  - [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.3
  - [ ] GIF Walkthrough: 
  
  
  ![XSS](https://user-images.githubusercontent.com/54424389/68551156-e3079b80-03d7-11ea-924a-6d8dbb1296be.gif)



  - [ ] Steps to recreate: 
    - First, we create a new post and set the editor to HTML edit mode. Then, we paste the code ```<a href="[caption code=">]</a><a title=" onmouseover=alert('test')  ">link</a> ```in the body. Finally, we click preview and hover over the link to see the message. 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/branches/4.2/src/wp-includes/class-wp-editor.php?rev=33361)

**2. (Required) Vulnerability Name or ID: Unauthenticated Stored Cross-Site Scripting (XSS)**
  - [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.1
  - [ ] GIF Walkthrough: 
  
  
  ![XSS_2](https://user-images.githubusercontent.com/54424389/68552047-cae84a00-03e0-11ea-8c48-39b32a557d31.gif)


  ![XSS_3](https://user-images.githubusercontent.com/54424389/68552049-cde33a80-03e0-11ea-80aa-fd31aff560dc.gif)


  - [ ] Steps to recreate:
    - An unauthenticated user injects Javascript code through making a comment that is long enough to be truncated when inserted in the         database. Once the comment is seen and approved by admin, the unauthethicated user's code will be executed.
  - [ ] Affected source code:
    - [Link 2](https://core.trac.wordpress.org/changeset?sfp_email=&sfph_mail=&reponame=&new=32311%40branches%2F4.2&old=32300%40branches%2F4.2)

**3. (Required) Vulnerability Name or ID: Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds**
  - [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.13
  - [ ] GIF Walkthrough: 
  
  
  ![YouTube](https://user-images.githubusercontent.com/54424389/68553084-308e0380-03ec-11ea-9d3c-e51b2b68c962.gif)



  - [ ] Steps to recreate: 
    - Make a new post with the format set to "Video." Paste the code ```[embed src='https://youtube.com/embed/12345\x3csvg onload=alert(1)\x3e'][/embed]``` in the body. Each time we preview the post, we will see an alert box with the message "1" pop up.
  - [ ] Affected source code:
    - [Link 3](https://github.com/WordPress/WordPress/commit/419c8d97ce8df7d5004ee0b566bc5e095f0a6ca8)

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [2019] [Jonathan So]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
