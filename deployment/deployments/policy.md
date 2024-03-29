# Policy edit

User can change policy settings assigned to endpoint if organization admininistrator allowed it in policy settings. To check or edit assigned policy just click the name of policy on it on dashboard. In example "policy1"

![](../../.gitbook/assets/assignedpol1.PNG)

For quick assigning just click appropriate document type in "Applications" tab.

![](../../.gitbook/assets/clipolicyset1.PNG)

* Select "My Documents" to add "My Documents" folder and subfolders to backup, ie. "C:\Users\user\Documents...\"
* Selecting "Office" will add all office type documents\(\*.doc, \*.docm, \*.docx, \*.dot, \*.pot, \*.potm, \*.potx,  \*.ppam, \*.pps, \*.ppsm, \*.ppsx, \*.ppt, \*.pptm, \*.pptx, \*.sldm, \*.sldx, \*.xla, \*.xlam, \*.xlm, \*.xls, \*.xlsb, \*.xlsm, \*.xlsx, \*.xlt, \*.xltx, \*.xlw\) on every disk on system.
* Select "**Desktop**" to add the desktop folder and all subfolders on it to backup.
* Select "**Email**" to add and schedule mailbox files for backup. **MS Outlook** and **IBM Notes** are only supported.
* By selecting "**Photos**" you will add all graphic files \(\*.bmp, \*.gif, \*.jpeg, \*.jpg, \*.png, \*.psd, \*.raw, \*.tga\) on all disks to backup.
* By selecting "**Music**" will add most common audio format files \(\*.flac, \*.m4a, \*.m4p, \*.mp3, \*.wav, \*.wma\) on all disks to backup.
* To simply add all video files format \(\*.avi, \*.flv, \*.h264, \*.hdmov, \*.mkv, \*.mp4, \*.mpe, \*.mpeg, \*.mpeg1, \*.mpeg4, \*.mpg, \*.mpg2, \*.wmv, \*.xvid\) just select "**Video**" icon.

Selected items will change colour to blue.

![](../../.gitbook/assets/clipolicyset2.PNG)

On Advanced tab you have to select retention for every directory added for backup. Just scroll out "Policy" menu  the right of item.

\*.

![](../../.gitbook/assets/clipolicyset5.PNG)

There are the following preconfigured retentions to choose: 7Days, 14Days, 30Days, 365Days and Nolimit.

![](../../.gitbook/assets/clipolicyset3.PNG)

You can add a directory manually to backup by clicking ![](../../.gitbook/assets/addinclude.PNG)and fulfilling _Directory_, _Extension,_ and retention _Policy_ fields.

![](../../.gitbook/assets/clipolicyset4.PNG)

To exclude some directories or/and file formats from the backup just choose 

![](../../.gitbook/assets/addexclude.PNG) button and fill the _Directory_ and file _Extensions_ fields to exclude them from backup.

For directory recursion just use: "...\" wildcard in the directory field. Without this wildcard, the KODO client will exclude or include selected folders only, not subfolders.

