#**Converting from Eagle to KiCad.**

The following 4 **ulp** (eagle user script file),  work in together or partly stand alone to  
converts **Eagle**  *sch/lbr's* version 6.xx file(s) to **KiCad** *sch* and *lib/mod* files.  

The Programs will do:  
1. - Eagle multi sheet sch to KiCad  multi sheets.  
2. - Global and local net labels for multi sheets.  
3. - Multi part gate's.  
4. - Build KiCad PCB modules and SCH libs from Eagle SCH.  
5. - Make project director to store all the converted files.  
6. - And basic error checking.  
7. - Eagle 6.xx PCB files can be directly import to KiCad.  

By using the  the following **ulp's**  a consistent link from the SCH to PCB is maintained  
So forward and backwoods net list annotation will work in KiCad!  

###Installing.
Download the as the zip file, (*click on the Button to the your bottom right on this page*. **Download ZIP**)  
And unzip using your favorite zip program to your target directory.  
&nbsp;**OR if your prefer git**  
git clone https://github.com/lachlanA/eagle-to-kicad.git  

**WARNING:**  The ULP's filename will conflict with Eagles ULP's filename's so don't install them in Eagle's  
ULP directory.  

There are 4 **ulp's** which have been hack together.  

1: ***renumber-sheet.ulp*** .......................   stage 1:  Add missing number(s) to parts Prefix's.  
2: ***eagle6xx-sch-to-kicad-sch.ulp*** ....   state 2:  Build sch and project files, etc  
3: ***exp-lbrs.ulp*** ......................................   stage 3: *automatically runs*  Extract libs from  eagle SCH/PCB  
4: ***eagle-lbr2kicad-1.0.ulp***................  stage 4:  *automatically runs* Convert Eagle lbr to KiCad lib/mod  
 
####HOW TO RUN THE ULP'S 
 
**WARNING Always backup your Eagle SCH/PCB files before running this program!**  

**1:** Start your Eagle program *(Make sure your using  version 6.xx of Eagle)*  

**2:** Open the eagle SCH/PCB  file you wish to convert.  
   Make sure the eagle SCH and PCB file's are both, Correct and pass all ERC/DRC checks in Eagle.  

**3:** Next Open  the top left hand  File menu and select  Run ULP  

**4:** A file requester window will open.  Using this, to select find or type the location of  
&nbsp;&nbsp;the ***renumber-sheet.ulp*** ULP you download from this website.  
&nbsp;&nbsp;We use this script to make sure all part prefix's are ending in a number  IE:   R0,  X1   etc.  
&nbsp;&nbsp;As KiCad will ask to renumber any prefix which dose not end in a number.  
&nbsp;&nbsp;*(It may do this any way, but don't worry it wont change any Prefix's which have already  
&nbsp;&nbsp; been numbered unless you tell it too!)*  Keeping prefix's consistent from SCH to PCB  
&nbsp;&nbsp;will allow net-list forward and back annotation to work in KiCad.  
&nbsp;&nbsp;Select **OK** *(this will run the scrip)*.  When this completes all references with out a number, should have  
&nbsp;&nbsp;a number appended to them.   Note: This number will start from the largest reference number on the SCH/PCB.  
        
**5:** Next Open  the top left hand  File menu and select Run ULP  
&nbsp;&nbsp;Using this, to select the location of the ***eagle6xx-sch-to-kicad-sch.ulp*** you downloaded.  
&nbsp;&nbsp;Select OK (this will run the scrip) There are many options most most should just work OK.  
&nbsp;&nbsp;Make sure you make/select a ***clean target directory*** where all the KiCad file's will be put.  
&nbsp;&nbsp;Select OK, And with luck you should have SCH part done.   The previous ULP will link automatically  
&nbsp;&nbsp; to ***exp-lbrs.ulp*** for the  next step:  
&nbsp;&nbsp;If you have selected extract the KiCad lib's from Eagle SCH/PCB *(The default).*  
&nbsp;&nbsp;This  ULP will build  Eagle lbr file,  *Note: this can be a very slow process,  and will  
&nbsp;&nbsp;leave the Eagle PCB editor window open when complete*. Just ignore this for the moment.  
&nbsp;&nbsp;If this complete OK, the previous ULP will link to ***eagle-lbr2kicad-1.0.ulp*** which will convert the Eagle lbr file  
&nbsp;&nbsp;to a KiCad lib/mod file's.  The ***eagle-lbr2kicad-1.0.ulp*** window window will open with quite a
&nbsp;&nbsp;few options. Just select OK for the moment.  And if *Murphy's Law  is sound asleep* we should have
&nbsp;&nbsp;the target directory with all the converted files, including KiCad project files.
&nbsp;&nbsp;But with one exception, it will be missing KiCad PCB file.  

**6:** For this, we need to Open KiCad's **pcbnew** program directly,  at the command prompted.  
&nbsp;&nbsp;*(Don't ask me why you can't do it from KiCad directly)* If you make the mistake of not opening
&nbsp;&nbsp;**pcbnew** directly, instead chose to run the KiCad **pcbnew** form the menu.  
&nbsp;&nbsp;You will have no option for importing the Eagle 6 PCB file!  
&nbsp;&nbsp;Click on **File->Open** in **pcbnew** an window will pop-up, and on the far Bottom wright you will have a  
&nbsp;&nbsp;drop down menu box option to select the type in import file.    Select version 6.x  XML  of Eagle, and  
&nbsp;&nbsp;the PCB eagle file linked to the eagle SCH file we used at the beginning and press OK.  
&nbsp;&nbsp;Now if it imported OK,  **SAVE AS** to your new target directory
&nbsp;&nbsp;(where you saved all the output of the preceding programs too) and type/append  
&nbsp;&nbsp;**project-name**.**kicadpcb** for the new KiCad PCB.  
&nbsp;&nbsp;All being well you should have  a converted eagle SCH-PCB correctly linked and referenced.  

NOTE'S:   For more info on KiCad  http://www.kicad-pcb.org/display/KICAD/Installing+KiCad  
&nbsp;&nbsp;As KiCad is the process of major upgrade,  and enhancement  please be nice asking ?  
&nbsp;&nbsp;of the Development team.  I think you  will love the new Push and Shove router,  
&nbsp;&nbsp;that feature alone make's it worth while moving from Eagle to KiCad  
&nbsp;&nbsp;I hope the ULP's  make the job a lot easy.  

&nbsp;&nbsp;Lachlan.  


  



