#Migrating Journals in Open Journal Systems

At UNB, we are limited to how we can migrate content both *into* and *out of* our Open Journal Systems (OJS) instance. This is largely because our instance of OJS is multi-journal (meaning that all of our journals are on one installation of OJS instead of the somewhat more common occurance of a journal having it's own isolated installation). Since the broader OJS mySQL database applies to all of our journals, pulling out the relevant material for just one journal is non-trivial. Such a process would be something like carving a piece out of the middle of a cake without disturbing the outer layers or sides. 

> This guide will *not* help you migrate a stand-alone installation of OJS with only one journal. 

Luckily, there are a few steps we can take in migrating large portions of useful content using OJS's built-in tools and a little elbow grease. Err... finger joint grease? Like, you're just typing and clicking really. Anyway... 

##What's included in "migration"?

Migration is, essentially, just the process of taking a the content of an OJS journal that's on one server and putting it on another server. In situations where the journal is entirely self-contained, this would be a pretty trivial problem to solve for systems staff or folks comfortable with server-side back-end admin work. However, migrating something from a multi-journal to singular, singular to multi-journal, or multi-journal to multi-journal instance of OJS requires a lot more fidgeting. 

The things you'll need to migrate include:

- issues and articles
- users
- copy (the website text and information)
- material currently in the peer review process

OJS supports both *export* and *import* of:

- issues and articles
- users

> As you can see, we are at an *impasse*.

This discrepency means that a huge portion of the content will need to be copied and pasted from one site to the other, manually. This includes any specific information from:

- setup
- subscriptions
- authors guidelines
- journal section policies (sections will be created as articles are imported)
- or, any custom content in static block or static page plugins... 

Those performing migrations will likely need to be logged into both websites as they copy content from one site to the other. If that isn't enough of a bummer, the other major issue is that there is no way to migrate the content from peer review. Your options are to keep two sites open until everything on one site is through the process, or asking your authors to resubmit on the new installation. Their credentials will be the same (if you've successfully migrated users), but their submitted, in editing, or in review papers *cannot* be migrated using OJS's interface. 

##Import/Export

OJS has a number of Import and Export Plugin features. Anyone with the role of **Journal Manager** can see and access them. Under the subheading "Management Pages", users may click on the link **Import/Export Data** while logged in as a Journal Manager to see their options. They are as follows:

- QuickSubmit Plugin: One-step submission plugin (*for submitting content to a journal while bypassing the editorial/peer review process*)
- DuraCloud Import/Export Plugin: Archive and restore issues using an external DuraCloud service for storage
- Public Identifiers XML Plugin: Import and export public identifiers
- DOAJ Export Plugin: Export Journal for DOAJ and supply journal information for inclusion
- **Users XML Plugin**: Import and export users 
- CrossRef XML Export Plugin: Export article metadata in CrossRef XML format. (*DOI Related*)
- PubMed XML Export Plugin: Export article metadata in PubMed XML format for indexing in MEDLINE.
- **Articles & Issues XML Plugin**: Import and export articles and issues
- mEDRA Export/Registration Plugin: Export issue, article and galley metadata in Onix for DOI (O4DOI) format and register DOIs with the mEDRA registration agency. (*DOI Related*)
- DataCite Export/Registration Plugin: Export or register issue, article, galley and supplementary file metadata in DataCite format. (*DOI Related*)
- METS XML Export Plugin: Export Journals in METS XML
- Erudit Article Export Plugin: Export articles using the English Erudit DTD

The two plugins needed for migrating content to OJS are the **Users XML Plugin** and the **Articles & Issues XML Plugin**. Journal Managers may import *or* export users or articles/issues. For each item exported, OJS will create a single XML file for that item. If you export one article, you will be downloading one XML file. If you export whole issues, you'll be downloading one XML file for the number of items you chose to download. 

There are three very important things to remember as part of this process:

1. Any galleys belonging to articles will be encoded – using base 64 – in the XML file that gets exported. You don't need to worry about HTML or PDF galleys. They will be preserved. 
2. There are likely file-size or memory limits on the server you're running OJS on. Exporting too much at once is likely to fail and you might not even get much of an error when it happens. It's best to chunk up your exports and imports by probably no more than a few issues at once, and possible just one issue at a time. 
3. It is unlikely that HTML galleys will be fully functional, depending on the CSS used on the site and where images might have been hosted. There may be some work on the part of the *importee* to tweak HTML for display on a new server. There isn't really anything that can be done on the export side to remedy this. 

###Users

####Exporting Users

Exporting users is tremendously simple. On the old/original installation of OJS, go to:

```
Journal Manager > Import/Export Data > Users XML Plugin
```

You can either export by role or export all. Unless you want folks to have to re-register or something, or you want to clear out potentially irrelevant roles, you can click on "export all". You'll be asked to save the XML file. That's it! 

####Importing Users

Importing users is only a little more complicated. On the new installation, do as you did before and navigate to:

```
Journal Manager > Import/Export Data > Users XML Plugin
```

You can select the file for import, as well as two other options. The first is to email every registered user with their username and password. That's largely up to you, if you think it's relevant. The second is to continue the import if there is an issue with one of the users. This is generally recommended, because OJS will give you a report of user conflicts or complications after you click the import button. 

The next page allows you to edit the records going into OJS. You can choose to omit some users, change their email address or name metadata, and select the role for those users. To click on multiple roles, hold down the CTRL key if you're a Windows user or the CMD key if you're a Mac user. This way, you can tweak all roles for all users, if necessary. 

> It's possible that, in importing users, OJS might require said users to change their passwords when they next login. It's probably a good idea to send a notification out to all users from the editor "notify users" tool. 

###Articles and Issues

####Exporting Articles and Issues

Exporting users is tremendously simple. On the old/original installation of OJS, go to:

```
Journal Manager > Import/Export Data > Articles & Issues XML Plugin
```

You only have two options for export, by article and by issue. You'll know which is appropriate based on what you're up to. OJS will save a copy of the issue or article as an XML file that contains all of the metadata necessary to import it back into OJS. It uses OJS's *native.dtd*. It also saves the contents of galleys in base64 encoding so they will also be re-created on import. 

####Importing Articles and Issues

Importing users is even easier! There's only one option. You simply click the "choose file" button find the file you wish to import, then click **import**. It'll do the work for you from there! 

##Summary and Notes

Again, this migration process is very simple and won't cover all of your bases for fully migrating a journal between two installations of OJS. The import/export plugin on covers a percentage of the work you'll need to do to migrate content. A full migration will require close attention to detail. Be prepared for any or all of the following:

- All journal copy (about the journal, author guidelines... etc.) will need to be copied from one "journal page" to the other. This could include:
	- The contents of **Journal Manager > Setup**.
	- The contents of **Journal Manger > Journal Sections** (although sections will be created in migration, their policies and options will not). 
	- The contents of **Journal Manager > Subscriptions**. 
	- The contents of **Journal Manager > Payment** (if PayPal is configured, you'll need to copy those settings over as well).
	- The contents of **Journal Manager > Languages**  should be checked to ensure that the same number of languages are enabled and the settings between each journal match. *native.dtd* has elements for locale, and will populate those fields accordingly, but they will not display if languages are not properly configured.
	- The contents of **Journal Manager - Masthead** should be configured *after* importing users.
	- The contents of **Journal Manager - Prepared Emails** might need to be altered if the editor made any adjustements to the system's automatic emails. 
	- Check **System Plugins** for both installations to see if there are any you're missing or aren't configured. Of note, especially, would be **Google Analytics** or other stat tracking plugins. You'll need to configure a Google Analytics account specifically for that journal. Also check **Static Page** and **Custom Block** plugins. 
- CSS for the journal will need to be migrated. If you have HTML galleys, this is particularly relevant. You may need to write whole new CSS, depending. 
- Any content currently in the editorial process cannot be migrated in any convenient way. You'll have to either resubmit that content as an editor, on behalf of those users, or keep the submissions going on one page until the cue is empty. 

GOOD LUCK. YOU CAN DO IT, I BET. 