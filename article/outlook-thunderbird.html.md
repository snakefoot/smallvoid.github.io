---
title: 'Changing from Outlook Express to Mozilla Thunderbird'
date: '2007-07-02T07:44:00+02:00'
status: publish
permalink: /article/outlook-thunderbird.html
author: Snakefoot
excerpt: 'Solutions to the different barriers that can keep one from moving to Thunderbird.'
type: post
id: 642
category:
    - Thunderbird
tag: []
post_format: []
---
[Mozilla Thunderbird](http://www.mozilla.com/en-US/thunderbird/) is an E-mail client which has grown very mature, and for me capable of replacing Microsoft Outlook Express.  
- Standard spellchecking with the ability to change between dictionaries
- Integration with most webmail services like Gmail, Hotmail and Yahoo
- Enhanced spam protection
- Styling through themes
- Extensible through [plugins](https://addons.mozilla.org/en-US/thunderbird/) which makes it possible for the community to add almost any feature.
 
 After the default installation of Thunderbird, then one will discover different things:

##### Delayed sending of e-mail

 When pressing send in Outlook Express, then the e-mail will be placed in the Outbox, and the next time it synchronizes with the mail-server then it will be sent. Thunderbird will immediately send the email, so if used to be able to edit a sent e-mail by going to the Outbox then you will be disappointed.  
[MagicSLR](https://addons.mozilla.org/en-US/thunderbird/addon/902) can replace the Send button with a Send Later button, which places the email in the Unsent folder. 

##### Reply and forward header are awful

 When replying to a mail then one doesn't get the pretty header showing the details of the message replying to. Instead one get the following:
 
> \[Author\] wrote:"

 [TB Reset Quote Header Extension](http://forum.addonsmirror.net/index.php?showtopic=1322) ([Change Quote](https://nic-nac-project.org/~kaosmos/changequote-en.html) / [smarttemplate4](https://addons.mozilla.org/en-US/thunderbird/addon/smarttemplate4/)) can create a reply-header based on templates files [quoteHdr.txt](/tweak/windows/files/quotehdr.txt) and [quoteHdrHtml.txt](/tweak/windows/files/quotehdrhtml.txt).
 
##### Reply will perform quote with indent character

 There is no option in Thunderbird to disable indent of the reply quote or change the indent character. This can lead to quite obscure emails when replying back and forth between two e-mail clients each with their own idea of how to indent.  
[QuoteAndComposeManager](https://nic-nac-project.org/~kaosmos/realborders-en.html) can remove the indent character when making a reply.

##### Using Thunderbird Address Book for mailing lists

 Windows Address Book can create groups, where one can just drag the wanted members into. In Thunderbird Address Book one can create lists, but when trying to drag a contact into the list nothing happens. Apparently the idea is that when doing a normal drag-drop then one is performing a copy, and because one should not copy contacts into lists, then it is rejected. Instead one just have to remember to hold down the CTRL-key when dragging contacts into a mailing list.