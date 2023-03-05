---
title: 'Using the Group Policy Editor as registry editor'
date: '2001-01-31T13:03:52+01:00'
status: publish
permalink: /article/winnt-group-policy-registry.html
author: Snakefoot
excerpt: 'How to use the group policy editor for easy editing of registry settings.'
type: post
id: 37
category:
    - Tips
    - Tips
    - Tips
tag:
    - group-policy
    - regedit
post_format: []
tags:
    - 'group-policy,regedit'
---
The Group Policies have been created to enable administrators of corporate networks to easily configure settings for a vast collection of computers and users. To start the **Group Policy Editor** (GPE) run this command (WinXP Home doesn't have this):

> gpedit.msc

 There is a premade custom GPE called **Local Security Policies** (Can be found in Administrative Tools), which only shows the "Local Computer Policy" -&gt; "Computer Configuration" -&gt; "Window Settings" -&gt; "Security Settings" (WinXP Home doesn't have this):
 > secpol.msc

 To create a custom GPE (Like SecPol.msc):
1. Start Microsoft Management Console (MMC) with this command:
 > mmc.exe
2. Select the "Console"-menu and click "Add/Remove Snap-In"
3. Press the Add... -button, Select "Group Policy", Press the Add-button, Press Finish-button and Press Close-button.
4. Select the newly added "Group Policy"-snapin and select the Extension-fan.
5. It is possible to uncheck policy extensions that are not interesting.
6. When finished press Ok and one can now fiddle with the custom GPE.
7. To save the custom GPE select the "Console"-menu and click "Save As..."
 
 More Info [MS KB271135](http://support.microsoft.com/kb/271135 "Windows 2000 Microsoft Management Console and Snap-in Restrictions [Q271135]")  
  
 Note it is possible to add extra ADM templates to the GPE, which allows one to configure even more options:
1. Start **GpEdit.msc** (WinXP Home doesn't have this)
2. Select one of the two **Administrative Templates** nodes
3. Right-click the selected node and select **Add/Remove Templates...**
4. In the new window press **Add**-button and f.ex. select **WuAu.adm** and press **Close**
5. Expand **Local Computer Policy** -&gt; **Computer Policy** -&gt; **Administrative Templates** -&gt; **Windows Components**
6. The new **Windows Update** node should now be seen (Contains options for configuring AU policies)
 
 Note it is possible to create custom ADM templates with own registry settings, that can be used by the GPE. The ADM template is a simple text file that can be edited with a text editor like Notepad [MS KB323639](http://support.microsoft.com/kb/323639 "HOW TO: Create Custom Administrative Templates in Windows 2000 [Q323639]"). There also exists tools like [PolicyMaker Registry Extension](/article/policymaker-registry-extension.html) that makes it a little easier to create custom ADM files.  
  
 Note the GPE shows by default only policies, and not preferences that are located in non-policy areas of the registry. The difference between policies and preferences is when a link to a policy .ADM file is removed then policies are removed but preferences stays.To also see preferences start GPE, select View, Filtering and clear the "Only show policy settings that can be fully managed".  
  
 Note if not using the GPE for applying registry settings, then one can disable the applying of Group Policies to increase startup performance:
1. Start **GpEdit.msc** (WinXP Home doesn't have this)
2. In the left tree select the root **Local Computer Policy**
3. Right-click the root and select **Properties**
4. Tick **Disable Computer Configuration settings**
5. Tick **Disable User Configuration settings**
6. Press **Ok**-button
 
 More Info [MS KB816662](http://support.microsoft.com/kb/816662 "Recommendations for Managing Group Policy Administrative Template (.adm) Files [Q816662]")