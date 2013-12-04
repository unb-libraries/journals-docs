# Tournesol Installation Guide:
For Windows (Mostly): A “Guide” by Mike Nason, June 2012: A Rope of Sand.

It's pretty easy, you guys.

**1)** Grab the TournesolBundle.zip file from the dev server. You can find it by going here:

```
//hilstorage.hil.unb.ca/journals
```

(How you get here might vary, depending on your operating system. You'll do it the way you do it to work on Journals though. I hope you know how to do that. If you don't, read the “Getting Started” guide for information on connecting to the etc_journals production server!)

**2)** Move it on over to your desktop, or wherever you might want to run Tournesol from. Or, howabout, I just say “move it over to the directory in which you want to run Tournesol.

**3)** Unzip!

**4)** You'll have two folders in here. One contains the Tournesol client itself. The other contains the “Required Programs” you'll need to run Tournesol. Open up “Required Programs”.

**5)** There are five (count 'em) things here. They're pretty straightforward.

- Image Magick (open the folder, run the installer)
- Ghostscript/gs900w32 (open the folder, run the installer)
- Adobe Reader/adbeRdr1012_en_US (run the installer)
- Java Runtime Environment/jre-7u2-windows-i586 (run the installer)
- Mozilla_XULRunner (so, for this one, copy the folder and open up your “Program Files” directory. Paste the folder in “Program Files”, open it up, and double click on “install.bat”. It might also just say “install”.

You're so close… you can taste it. It reminds you of something you ate as a child. But digital.

**6)** Open up the tournesol directory.

**7)** Open the directory called “config”.

**8)** Open “configuration.xml”, ideally in Oxygen XML Editor. (or whatever, I trust you)

**9)** Scroll down to line 63. You should see something that looks like this:

```
  <!-- The remote repository for keeping all necessary files with '/' as separator -->     
  <remote>         
    <useRemoteReposistory>true</useRemoteReposistory>         
    <remoteRepository>             
      <path>Y:\tournesolRepository</path>         
    </remoteRepository>     
  </remote>
```

This is the only thing you should need to configure. Open up your files browser (“My Computer” or whatever) and check to see what letter is next to your samba connection to “journals”. That letter is what you edit in this piece of code. So, if you see something like: “journals on 'psf' (X:)” then that letter needs to be changed in your Tournesol configuration file. In this case, I would be changing it to this:

```
  <!-- The remote repository for keeping all necessary files with '/' as separator -->     
  <remote>         
    <useRemoteReposistory>true</useRemoteReposistory>         
    <remoteRepository>             
      <path>X:\tournesolRepository</path>         
    </remoteRepository>     
  </remote>
```

Please note: If, at any point, you don't seem to be properly pushing or pulling your content from Tournesol, give this configuration step a once over and make sure the letter for your journals connection hasn't changed. It shouldn't, probably, but it might, depending on how many drives you have mounted. If something else has taken “X”, then it will be a “Y” instead. This is especially the case if you're using Tournesol on a Mac through a virtualized Windows installation (whoa).

At this point, you can go back to the “Tournesol…” directory and run the software.

That's it, you're ready to read the Tournesol Markup Guide!

CONGRATULATES