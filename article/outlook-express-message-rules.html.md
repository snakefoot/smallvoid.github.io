---
title: 'Take advantage of message rules in Outlook Express'
date: '2002-05-18T18:34:09+02:00'
status: publish
permalink: /article/outlook-express-message-rules.html
author: Snakefoot
excerpt: 'Outlook Express can be configured to perform certain actions when an email is received, which is expressed in message rules.'
type: post
id: 332
category:
    - 'Outlook Express'
tag:
    - message-rules
    - spam
post_format: []
tags:
    - 'message-rules,spam'
---
It is possible in Outlook Express(OE) to use rules, to automatically sort and filter your email. To configure rules in OE one has go to the menu and select "Tools" -&gt; "Message Rules" -&gt; "Mail..."

##### Sort your private mail:

 If you have a dear friend from who you want to save the letters you have gotten. Then create rule "Where the from line contains people" and let the people be your dear friends email address. Then "Move it to specified Folder" (Friend)  
##### Sort your work mail:

 If you have a tendency to get mail at home from work, which you don't want to clutter with your private mail. Then create rule "Where the from line contains people" and let people be your "company.com"(This will take all emails from company.com). Then "Move it to specified Folder" (Work)  
##### Sort your mail accounts:

 If you receive mail from several accounts, and want to sort the incoming mail to different local folders. Then create rule "Where the message is from the specified account" and let account be your incoming mail account. Then "Move it to specified Folder"  
##### Remove spam which includes spam related content:

 Message rules can be used as kill filter for spam email. Create a rule "Where the Subject line contains specific words" - university diplomas
- home loans
- accept credit cards
- sign up today
- ...
 
 Then "Move it to specified Folder"(Junk) or "Delete it"

##### Remove spam which is not using your email address:

 Sometimes spam is sent out without your email address is being part of To- or CC- line (A verified email is worth money and they don't want to share it with others without getting money). To handle such mails create rule "Where the To or CC line contains people" and let people be your own email addresses. Then while still in the window where you add people press the "Options..." and negate the expression so it becomes "Where the To or CC line does not contain". Then "Move it to specified Folder" (Junk).  
##### Remove spam which is not sent with valid email address:

 Sometimes spam is sent out with no proper from email address, to make sure you can't reply back or easily report them. To filter away such mails create rule "Where the From line contains people" and let the people be "@". Then while still in the window where you add people press the "Options..." and negate the expression os it becomes "Where the From line does not contain". Then "Move it to specified Folder" (Junk).  
##### Remove spam which uses your own email address as source address:

 Sometimes spammers don't have the imagination to create a dummy address and uses your email address both as sender and receiver. To filter away such mails create rule "Where the From line contains people" and let people be your own email address ex. "sweaty1@hotmail.com". Then "Move it to specified Folder" (Junk).  
##### Remove spam which comes from certain domain/email:

 This can be done by creating a rule which contains domains/emails addresses which are sending you spam often and move them to a junk folder. Or more drastically block certain domains/email addresses and have the emails from those addresses deleted at once.  
##### Things to remember about spam rules:

- Make sure that your spam rules is in the bottom of the rule list.
- If you receive mail which acts very much spam but isn't, then create special rules for those, which then are placed above the spam rules. 
  - Ex. some mailing lists uses Blind Carbon Copy(BCC), so your email address is not part of the To- From- line. This is done to avoid revealing the addresses in the list for spammers to use.
  - Ex. some companies has automatic systems which can sent out confirmations and similar things. But the From email address is faulty because one should not reply back to the automatic system.
- Spam rules are only made upon assumptions, so your spam filter might sort away some useful mail by accident.
- Detected spam should be reported to [Spamcop.net](http://spamcop.net)
 
 Related [Backup your Outlook Express Rules](/article/outlook-express-backup-rules.html)