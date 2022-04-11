Setting Up NX-GIC
---
if you haven't already download [NX-GIC](https://github.com/hotshotz79/NX-Game-Icon-Customizer).

When you first launch the program you will need to ```scan``` so you can pull the icon repos, there is also an offline method but I won't be going into that here.

![nxgic](<img/nx-gic.png>)
!!! Error "PLEASE NOTE"
	the icon repo is over 300mb in zip format with over 4700 extracting can be slow

Once complete we will set the switch ip for ftp transfers 
*within NX-CIG*

|	`File > Settings`	  |
|-------------------------|
|![ip](<img/settings.jpg>)|

| put your switch ip into the `Switch IP Address` textbox |
|--------------------|
|![ip](<img/ip.jpg>)|

!!! info "If you are unsure what your switch IP is open up FTPD on your switch, this is also the next step."

	open FTPD on your switch from the hbmenu and input the switch ip shown in ftpd into the FTP selection in nx-gic
	![ftpd](<img/nxftpd.jpg>)

	![nxgic](<img/ftpd1.jpg>)
	!!! warning "port number isn't required but must be set to `5000` which is the default port for ftpd"

##Installing NX Title List Dumper
---

with ftpd running on the switch lets install NX Title List Dumper from nx-gic

|`Title IDs > Install NX Title List Dumper (NRO)`|
|-------------|
|![nxgic-tid](<img/nx-gic-tid.jpg>)|

Follow the instructions on the popup.

![nxgic](<img/popup1.jpg>)

Our Switch IP Should Be here.
hit `yes` and the process will begin

!!!info "Manual Installing NX Titles List Dumper"
	if you want to install manually hit `no` and you'll be taken to [nx-titles-list-dumper](https://github.com/HamletDuFromage/nx-titles-list-dumper/releases) 
	
	download the and place the .nro into `SD:/switch/`

![yes](<img/yes.jpg>)

hit `yes` you will get a popup 

![yes-popup](<img/yes2.jpg>)



###Using NX Titles List Dumper
---

Once the nro is transferred  load nx-titles-list-dumper from hbmenu

![nxgic](<img/nxtitledump.jpg>)

![nxgic](<img/nxtitledump2.jpg>)

press `(A)` to dump your installed title IDs

into `SD:/titles.csv` once it's `done` 

press `+` to exit

once `SD:/titles.csv` is dumped, open ftpd from the hbmenu again

![ftpd](<img/nxftpd.jpg>)

and hit `ok` in NX-GIC

![ftpd](<img/ok.jpg>)

!!! Warning
	if the ftp transfer of ***`titles.csv`*** fails (mine unfortunately did)

	place `titles.csv` ___from___ the `root` of your SD card into the same folder as `NX-Game Icon Customizer.exe` 

	![ftpd](<img/yes3.jpg>)


![cvs-complete](<img/done2.jpg>)


# Auto NX-GIC
---

Auto nx-gic can be used automatically select icons based off the installed titleIDs on your switch via `titles.cvs`
from the NX Titles List Dumper homebrew

![nxgic](<img/auto-nx-gic.jpg>)

Click on `Auto GIC` to enable it 

then from the drop down select the `style` to match your installed theme

in this example I've chosen *vertical*

now nx-gic will match all of the icons found in titles.csv to icons on the repo

click on `Add All to Output` to add the matching icons to the upload queue

!!! Warning "Missing icons?"
	you may notice some icons aren't found or matched this can be due to 1 of 2 reasons
		
	1. The Icon Doesn't exist.
	2. The title ID you have is different from the title ID on the repo (US/EUR/JPN).

  	homebrew forwarders are usually not matched so you will have to manually change the TID in the output section
  
 you can also add icons individually auto-gic pics the first icon found.
 
!!!info "my repo might have multiple variants for certain games, it might have older variations of a TID for homebrew between different icons"

## Showing Icons Based off TitleID 
---
 you can show icons matching installed TIDs by clicking

 `Title IDs > show Icons for Installed Games only`

  ![nxgic](<img/gic-showins.jpg>)

## View A List of installed Games
---
 you may also individually look through each icon folder and use the CSV list to match icons
 by clicking 
 
 `title IDs > Show List of Installed Games (CSV)`
 ![nxgic](<img/showcsv.jpg>)

#Editing your Output before tranferring
---

It's possible to edit your output before begining to transfer files to the switch

![nxgic-tidedit](<img/tid.jpg>)

you can edit titleID in the output section just by copying `CTRL+C` the titleID in the CSVlist and pasting`CTRL+V` the over titleID in output with your new titleID.

if your output has a game with a title you're unsure of like a japanese title in the example above

you can click on the `view` button and the icon will open and show you the image in the queue

You can set a `custom title` / `Author` & `Version` which is excellent for Fan translations

editing in NX-GIC will make a config.ini file and place it in the same folder as the custom icon
```
[override_nacp]
name=my custom title name game
author=someone
display_version=X.X.X
```
you can see Yo-Kai Watch is renamed from japanese in the example below

![yokai](<img/yokai.jpg>)

![vTheme](<img/notice.jpg>)

This isn't a permanent "rename" it works the exact same way the icon takeover does.

!!!info "The majority of my repo is based on US TID"
	you can also use this blazing fast TID/Game search database
	[https://titledblookup.stackblitz.io/](https://titledblookup.stackblitz.io/)
 
#Transferring
---

when you are happy with your chosen icon(s) click `transfer`


!!! note "FTPD should be open on your switch"

![ftpd](<img/nxftpd.jpg>)

hopfully you have already setup the IP of your switch as previously shown

![nxgic](<img/nx-gic5.png>)

click ```upload``` and you'll see the switch recieve the files, they're automatically transferred to the correct folders based off the titleID
in `SD:/atmosphere/contents/[titleid]/icon.jpg`

![nxgic](<img/ftpd2.jpg>)

once you've finished transferring you can close ftpd 

!!!Warning "You may need to reboot for icons to refresh"

##Recommended transfer method
---

I recommend using the ftp method over mtp as i personally find ftp to be faster, especially when you are bulk transferring custom icons, so that's the method I will be outlining in this tutorial.