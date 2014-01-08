# Images in Detailed Markup

## Introduction

You're going to come across images when you're working on detailed markup. They might be tables, figures, equations, simple photos, vector artwork... there are many examples. Occasionally, you'll even have to turn a piece of text that is merely *difficult to format* into an image (examples might include a very weirdly formatted letter or a paragraph with an equation in it – feel free to ask about whether or not something should be an image). This document is a guide on how to handle images in journals. It's definitely worth pointing out, however, that so long as you come up with the same result as this document (a reasonably-sized JPEG file in the proper directory and named to match the article file name), you can basically go about this however you like. 

The image capturing process is tedious but really, really simple. It works the same way every time, in a handful of steps:

1. Copy the image from the final article PDF.
2. Open that image in Photoshop.
3. Save that image as a JPEG.
4. Place the image in the ``/journalimages`` directory.  

As such, to do images work you'll likely need the following: 

- Adobe Acrobat
- Photoshop CS 3-5 (older versions work too... you'll just need *something*)

> **Please Note:** these steps are currently being reviewed and are pretty temporary. This process is subject to change and probably sooner than later. It's also worth noting that you may not actually need all of the tools listed here. This work can be done with a simple screen-grabbing or screenshot tool most of the time. The photo editing can be done by pretty much anything as well (like [The Gimp](http://www.gimp.org/)). You only need to **ensure that the file is a nice size** (not too small or compressed) and that it is saved in **JPEG format**. 

# Copying the Image From PDF

The first part of the process is to grab the image from the PDF. PDFs usually have large versions of images in them and we can get fairly sizable images to copy.

**1) Increase the Zoom Level to 150 or 200%**

We do this to ensure that the images are nice and large online. You might have images that are bigger than you can fit on your screen. That's ok. Please note, however, that *if an image is pixelated or blurry at this size, it's alright to go below 150%*. It's not worth having a large image if it's blurry from the start. 

**2) Find the "Snapshot Tool"**

Depending on your version of Acrobat, this might be in a few different places. In Adobe Acrobat X (that's ten... not ex), you can go to **Edit** on the menu bar and scroll down to the tool called **Take a Snapshot**. 

![image1](https://github.com/unb-libraries/journals-docs/blob/master/images/images1.png?raw=true)

In Adobe Acrobat 9, the snapshot tool appears on the toolbar. The logo looks like a little camera inside of a box. 

The Snapshot tool changes your cursor to one that can be dragged around images. Once you draw a box around the image you need to copy, let go of the cursor and it will copy it to your clipboard. *When you are dragging the box around the image, make sure that you also capture the caption for that image in what you are selecting*. This ensures that the user can see the caption when they open up the image afterwards. 

The copied image is now on your clipboard.

# Opening and Saving the Image In Photoshop

Run **Adobe Photoshop** and, once it's running, do the following. 

- Press Command (or, if you're on a Windows box, CTRL) + N. This opens a new file. 
- Press **OK** on the window that pops up. (Photoshop automatically sizes new images to be the same size as whatever is on your clipboard. This way, you don't have to worry about sizing your file). 
- Press Command + P to paste your image. 
- Next you need to **Flatten the image**. This is done by clicking on a small box in the top right of your **Layers Menu** (which ought to be on the right hand side of your screen) and selecting "Flatten Image". (Photoshop works with a layer system that allows you to layer your image editing. In order to save the file as a JPEG, however, we need to combine all these layers together. This is what "flattening" does.) 

![image2](https://github.com/unb-libraries/journals-docs/blob/master/images/images2.png?raw=true)

![image3](https://github.com/unb-libraries/journals-docs/blob/master/images/images3.png?raw=true)

- Once the image is flattened, press Command + S to save. 
- Make sure the file-type is "JPG"

![images4](https://github.com/unb-libraries/journals-docs/blob/master/images/images4.png?raw=true)

- You'll need to rename the file as well. The files have the same naming conventions as the XML, PDF, and HTML files you're working on. Some examples would be as follows:
    - ageo48art05_fig1.jpg (note the lack of a 0 between fig and 1... this is unusual in our workflow, but... I mean... here we are)
    - ageo48art05_ta1.jpg
    - ageo48art05_eq1.jpg
    - acad30_1art01_fig1.jpg
- Save the File. 

# Putting the Images Online

All of our images go in a directory structure that is separate but very similar to the structure we have for our XML files. They're nested in their own directory called ``/journalimages`` which can be found from your own **home directory**. You'll need to look in a folder called ``/ojs_storage`` Within ``/journalsimages``, you'll find a list of journal titles as they would appear in ``/etc_journals``. After that, year/volume/issue/files. So:

> /home/USERNAME/ojs_storage/journalimages/journal/year/volume/number/

The files need to be in this directory to be readable online. In order to double check, it's not a bad idea to look at the XML file for the article you're working on. After running **cleanUp**, you should see the file path for all of your images at the top of the XML file under the ``<grlien>`` element. These are created by **cleanUp** and you'll have to put the images in a matching directory. This process more or less requires the use of an **SFTP** client (Fetch, Filezilla, CyberDuck). You can ask systems for help if you don't know how to do this. 

And that's it! Do this for every image in every article you're marking up (**not including ads**) until you're out of images. Hooray!

# But what about this one weird image...

So, there are some exceptions for things, as you might have guessed. There are some unique or uncommon situations that still come up from time to time that you might need some guidance on. What follows is a short list of those sorts of images:

## A table or figure that spans two pages

This is actually more common than I'm letting on. In this case, the best bet is to copy both images and splice them together in photoshop. This involves increasing the canvas size and pasting both images in one file, using the hand or arrow tool to move the two layers around, and flattening once everything is properly positioned. 

**However**, if there are any situations where the second part of a split table has it's own header, it's best to just keep those separate. Feel free to ask someone about something you're confused by. 

## An image where the caption Somewhere Else

Sometimes the caption for an image is actually found in some place other than just below or above the image. For example, it might be beside the image and surrounded by text, or it might be on another page entirely. In these cases, it's best to crop the image, crop the caption separately, and combine them back together in photoshop. If the caption is to the side of the image, it's best to just leave the caption on the side but delete any extra text or imagery that maybe doesn't belong in the image. 

## Equations

Equations don't need to be zoomed in on the same way as regular images. You can copy those at a size of 125% or 100% without losing anything in the process. 