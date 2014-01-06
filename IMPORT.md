# Uploading to OJS

We upload a lot of content to Open Journal Systems (OJS). This guide will cover the variety of ways to get journal content into OJS. If anything you are looking to do isn't covered by this guide, please consult [OJS documentation](http://pkp.sfu.ca/ojs/ojs_documentation/) at the Public Knowledge Project website (it's really good and *super comprehensive*). Additionally, there's [PKP School](http://pkpschool.sfu.ca/) which is also maintained by PKP and has an extensive collection of tutorial videos for you to use. 

If you have any issues beyond what's in either this guide or PKP's documentation, feel free to ask for help on the PKP [Support Forum](http://pkp.sfu.ca/support/forum/). We have a great relationship with PKP, and they will be happy to help you.

Note: if anything in these guides isn't working correctly or at all, please email libsystems@unb.ca to submit a support ticket.

# Introduction

The *vast majority* of our registered OJS users upload content to the system in a way that's very different from how you'll be doing it. It's important to know the process, however, particularly if they come to you for help (and they will).

From the perspective of the Text Centre, most of the uploading is done via **Command Line** (though a "terminal" application like *Terminal* for the Mac or the freely-available [PuTTy for Windows](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html) users). This is done to upload whole issues at once and uses metadata from our **markup** and saving us a tremendous amount of time. This is referred to as "batch" uploading, because we publish entire issues at once this way. 

You may also need to upload individual "galleys". A **galley** is a file that users of the OJS website can read. It is the finished version of an article, primarily in either HTML or PDF format. This is a part of the **editorial process**, which is discussed more fully in other guides, but is worth reviewing here. 

# The roles and how they effect publishing:

- An **Author** can only submit articles through the default submission process. This process sends articles to peer-review.
- An **Editor** can submit articles through the default submission process and circumvent peer-review entirely, if they wish. They can also modify existing submissions and upload a "galley" to anything in the system.
- A **Journal Manager** can use the *QuickSubmit* feature to submit content or use any other import/export tools from the user interface.
- A **System Administrator** can batch upload issues from the command line and has access to any of the methods above, so long as they have enrolled themselves in Author, Editor, and Journal Manager roles for a specific journal. As an ETC staff member, you will have access to System Administrator functions. 

# The Article Submission Process

Article submission is how authors and editors submit their articles to journals for *peer review*. It is a really simple 5 step process where the user has to make sure the requirements for submission are met, enter article metadata, attach a file for upload, and attach any supplementary files. There are differences depending on who is doing the uploading.

## As an "Author" (how our users will mostly do it)

Authors can *only submit* content directly to peer review processes. They have the least amount of control.

Authors login to OJS and click on **User Home**. On the main screen showing the roles for journals to which they are members, they can either click on **Author** or **[New Submission]**. The article submission process is detailed fully in [PKP documentation](http://pkp.sfu.ca/ojs/docs/userguide/2.3.3/authorSubmission.html) and in our own [OJS Quick Reference Guide](http://journals.hil.unb.ca/static_content/site/OJS-quickref.pdf).

*Use Case*: other than walking a user through the process, hopefully none.
 
## As an "Editor" (how you and editors can do it)

Editors can submit content in the exact some way as authors. Some journal sections even require that the submitter is an editor. The process for submitting content to OJS as an editor is similar to that of regular authors, *with one exception*. On the very last page of the submission process, editors are asked if they'd like to skip the review process and move the content straight to editing. 

This allows editors to fast-track material that has been peer-reviewed outside of the system straight to an issue. It also allows editors to skip peer-review for small pieces like editorials or erratum. 

*Use Case*: You may be asked to add an article to an issue that is already published. This is one of two ways to circumvent the submission process for this purpose. 

# Uploading a Galley to an Existing Article

Sometimes a journal has already posted HTML or PDF galleys but there will be a need to either upload another galley or replace an existing one. This can be done by any **Editor** in OJS. The steps are as follows:

<!-- Steps here -->

# The QuickSubmit Plugin

The **QuickSubmit Plugin** provides a one-step submission process for editors needing to bypass the traditional submission, review, and editing process. This process is only useful for us ***in the very specific case where Erudit are not involved***. If XML is being produced for a journal, QuickSubmit should not be used. 

![screenshot](http://pkp.sfu.ca/ojs/docs/userguide/2.3.3/figures/jm_import_quicksub.png)

Once you have filled in the form, including the section, file to be uploaded (this would be a ready-to-publish PDF or HTML file), author information, title, abstract, keywords, etc., it will appear either in the selected issue or in the Editing section ready for scheduling to an issue (see Scheduling).

This is a useful tool for 5 - 10 articles, but if you have more than that, you should probably use the batch import process described below.

*Use Case*: You might have a one-off project where you only need to upload a few articles for either an existing issue or a whole new issue. QuickSubmit is one of the more flexible means for adding new articles to the system quickly if no galleys or metadata currently exist. 

# Batch Upload via Command Line

This is **the standard way** in which you'll have to upload journals content to OJS. It's standard because it's the easiest way to upload an entire issue at once. Also, it's gratifying.

It comes in some stages:

1. Creation of the ojs_import.xml file.
2. Proofing of the ojs_import.xml file.
3. Upload to Staging.
4. Proofing.
5. Upload live.

### Creation of the ojs_import file.

The ojs_import.xml file is a special file specifically for uploading to OJS. OJS has it's own [DTD](http://www.w3schools.com/dtd/default.asp) for importing the metadata you entered as part of the markup process into the system. *This file is the bridge between our Érudit-centric markup and our use of the OJS publication platform*. 

Before you run the command line scripts needed to make the file, you need to be sure you've covered everything on the following checklist.

- [ ] all XML markup is valid and complete.
- [ ] the **Transform** script has been run to create HTML versions of your work (*only a concern for detailed markup*)
- [ ] the HTML files are in the **HTML folder** with file names that match the PDF files and XML files
- [ ] images for the XML have been processed and uploaded to *ojs_storage/journal_images*
- [ ] there are no files in the HTML, PDF, or XML folders that you don't want uploaded. 

Once these conditions are met. You can open up your terminal application. If you need any help connecting here, you'll have to speak with library systems to get your account and access set up. 

> *A word on SSH and the terminal: before you use your terminal program for uploading content to OJS, you are encouraged to use the terminal to navigate around your computer. This will help you understand basic SSH commands like* **cd** *or* **mv**. *For more on SSH commands, simply find a guide about basic SSH navigation. I've provided a link to one [here](https://kb.mediatemple.net/questions/247/Common+SSH+Commands#gs).*

Starting from your home directory, navigate to the directory where the issue you're uploading resides. For example:

>`` user@server:~> cd journals/etc_journals/JCIM/2013/Vol_16/No_01/``

In this case, we're **changing directories** (cd) from our home directory to Volume 16, Number 1 of JCIM from 2013. If you type **ls -l**, you'll get a list of the content in the directory. It should look something like this:

>`` user@server:~/journals/etc_journals/JCIM/2013/Vol_16/No_01/> ls``
>``HTML  ojs_import.xml  PDF  SOURCE  XML``

From here, you run a command called **buildImportFile**. 

>``user@server:~/journals/etc_journals/JCIM/2013/Vol_16/No_01/> buildImportFile ``

This will create the **ojs_import.xml** file in your directory.

### Proofing of the ojs_import.xml File

There are a few things you'll need to check before you upload your ojs_import.xml file. While the script saves you a lot of work and pulls the majority of the metadata you need from the lite or detailed XML, there are some parts of the process that can't be automated. 

#### Current Publication

At the top of the file, there's are some XML Elements related to when the content was published. Specifically, you're interested in the following line.

>``<issue published="true" current="true">``

If you are uploading back-issues of a journal, you certainly won't be uploading the "current" issue. You should change the value to "false" in that case. Additionally, if you are uploading something into OJS as a "future issue" that won't be published immediately, you can change the *issue published* attribute to "false" as well. 

#### Dates

A publication date will be affixed to the issue *and every article* in the file. Make sure it's as accurate as you can make it. You should have done this in the XML markup. I hope you did. If not, go back and fix it in the XML markup and re-build your ojs_import.xml. 

If you need to make a change here, though, use a Find/Replace and do all of the dates at once. 

#### Section titles and Abbreviations

This is the biggest thing you'll need to pay attention to. If any journal has published in OJS before, there will have been specific Journal Section titles and Abbreviations for those sections in the journal. The script we use only does half the work. Section Titles in the file should match the ``<surtitre>`` tag in your XML. That's the tag that denotes what section your article goes in. But the default abbreviations the script makes are just all-caps versions of that title. 

That won't do at all. Here's an example of how it will look when you start looking at sections:

>``<section>``
>``<title>Editorial</title>``
>``<abbrev>EDITORIAL</abbrev>``

I can check existing Journal Sections by going into OJS:

>**User Home** -> **Journal Manager** -> **Journal Sections**

In this case, a fixed section would look like this:

>``<section>``
>``<title>Editorial</title>``
>``<abbrev>ED</abbrev>``

If you don't make this adjustment, OJS might either partially deny your upload (forcing you to delete the issue and start over) or will publish articles to a wholly new but redundant section. You'll then be faced with having to choose between existing, redundant sections. There is no easy way to delete sections without deleting the articles published to them, so try to just get them right from the start. 

#### Article Order

Articles are published to OJS in the order the appear in the ojs_import.xml file. It's important to remember that OJS can't alternate sections, however. You can't properly display two articles, a series post, and another article like certain tables of contents might. All content has to be grouped by section. Do your best to ensure that your sections are in descending order and appropriate. The script will automatically sort the content by page number, so it should be easy to do this. 

#### General Metadata Proofing

The ojs_import.xml file is an XML copy of what will be published in OJS online. The file is an excellent place to proof the metadata before posting the content online. *If you notice any issues with the content, you need to change them both in this file* **and** *in the XML.*

### Upload to Staging Site

Once your ojs_import.xml file has been thoroughly proofed and you're sure everything is in it's right place, you're ready to upload your issue to **journals-staging**. Journals-staging is an instance of OJS we use for proofing content before publishing it to our live site. While there are certainly situations where you won't have to upload to staging, it's generally good practice to use it as a final glance at your issue before it goes out into the world. 

> *Note: uploading to staging and uploading to live are very similar processes. Uploading to staging can be done repeatedly without much extra hassle. If you mess up uploading live, you'll have to delete content and clean up mistakes carefully. Practice with staging as much as you can until you're comfortable.*

First of all, you need to navigate to the folder the upload tool is in. 

No matter where you are, you can type in the following:

> ``cd /srv/www/journals-staging.lib.unb.ca``

From here, you can execute a full upload. Here's an example (pretend it's all on one line):

> ``user@server:/srv/www/journals-staging.lib.unb.ca> php tools/importExport.php``
>``NativeImportExportPlugin import``
>``home/YOURHOMEDIRECTORY/journals/etc_journals/JOURNAL/YEAR/VOLUME/NUMBER/ojs_import.xml ABBREVIATIONFORJOURNAL administrator``

So, let's break this down. You're choosing the server you want to upload an article to. Then you're running a php script called "importExport.php" which has a number of different commands. You're telling that script that you want to run *NativeImportExportPlugin*. "Native" is the name of the OJS DTD, so this is the plugin for running an *import* or *export* of something in the *Native DTD*. You want to run import, and you want to run it on a specific file, *for a specific journal*, as the OJS user, *administrator*. 

Hopefully, the other all-caps placeholders make sense, the least obvious is the "abbreviation for journal", which is the abbreviation in OJS for that particular journal. It's sort of a journal ID. It's how OJS knows which journal your publishing to. 

You can find out the journal ID by looking in a URL for that specific journal in OJS. The shorthand for that journal will be in the URL. For example, Geoscience Canada's is **GC**. Atlantic Geology's is **ag**. Acadiensis' is **Acadiensis**. Newfoundland Studies is **NFLDS**.

So, a completed issue of the Journal of New Brunswick Studies would look like this:

>``user@server:/srv/www/journals-staging.lib.unb.ca> php tools/importExport.php``
>``NativeImportExportPlugin import`` ``/home/mnason/journals/etc_journals/JNBS/2013/Vol_04/ojs_import.xml JNBS administrator``

If the upload is successful, you'll get a prompt that lets you know. If you get an error and you don't understand it, ask folks in systems for assistance. 

### Proofing 

After your issue is uploaded, you can look at the issue on staging. Proofing at this point is a little unusual. This is because – even though you can make changes to the content in the staging instance of OJS – any changes you make within OJS will not fix anything. If you notice errors, the best course of action is the following:

- [ ] change the original XML file
- [ ] mirror that change in the ojs_import.xml file
- [ ] re-upload to staging or wait until all changes are definitely fixed and upload to live. 

Once all the changes are made, you can upload to the live site. Finally. You did it. 

### Upload to Live OJS Site

Since uploading to live is a lot like uploading to staging, you should feel pretty confident at this point. There are very few changes. 

Before, our example looked like this:

> ``user@server:/srv/www/journals-staging.lib.unb.ca> php tools/importExport.php``
>``NativeImportExportPlugin import``
>``/home/YOURHOMEDIRECTORY/journals/etc_journals/JOURNAL/YEAR/VOLUME/NUMBER/ojs_import.xml ABBREVIATIONFORJOURNAL administrator``

For uploading to the live site, it's going to look like this:

> ``user@server:/srv/www/journals.hil.unb.ca> php tools/importExport.php``
>``NativeImportExportPlugin import``
>``/home/YOURHOMEDIRECTORY/journals/etc_journals/JOURNAL/YEAR/VOLUME/NUMBER/ojs_import.xml ABBREVIATIONFORJOURNAL administrator``

Did you spot the difference? For uploading to the live site, we need to be in the directory **/srv/www/journals.hil.unb.ca**. That's pretty much the only difference. 

# Eating Your Mistakes

But! You will inevitably upload content that you didn't mean to upload. Or, you'll upload content that is hosed and needs to be deleted and re-uploaded. That's a bit of an ordeal. Let's talk about it... 

