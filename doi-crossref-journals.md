#DOIs, CrossRef and OJS w/CDS Journals Services

*Mike Nason // Scholarly Communications Librarian // April 2015*

<!-- TOC depth:6 withLinks:1 updateOnSave:1 -->
- [Introduction](#introduction)
- [1.0 DOIs](#10-dois)
	- [1.1 What is a DOI?](#11-what-is-a-doi)
	- [1.2 How can I get DOIs?](#12-how-can-i-get-dois)
	- [1.3 What is CrossRef?](#13-what-is-crossref)
		- [1.3.1 Registering with CrossRef](#131-registering-with-crossref)
- [2.0 OJS](#20-ojs)
	- [2.1 How do I configure OJS for DOIs?](#21-how-do-i-configure-ojs-for-dois)
		- [2.1.1 How do I assign a DOI to an article?](#211-how-do-i-assign-a-doi-to-an-article)
		- [2.1.2 How do I submit or register DOIs?](#212-how-do-i-submit-or-register-dois)
	- [2.2 How do I configure the CrossRef Plugin in OJS?](#22-how-do-i-configure-the-crossref-plugin-in-ojs)
		- [2.2.1 Configuring the CrossRef Plugin](#221-configuring-the-crossref-plugin)
	- [2.3 Submitting DOIs using the CrossRef Plugin](#23-submitting-dois-using-the-crossref-plugin)
- [3.0 DOI's in Markup](#30-dois-in-markup)
<!-- /TOC -->

###Introduction

This document pulls content from a variety of areas including [CrossRef], the [PKP Wiki], [Wikipedia], as well as a few other sources. It is intended as a bit of a primer on the form and function of DOIs themselves, as well as some information on how they are managed, who manages them, and how [Open Journal Systems] can accomodate their use. Additionally, it serves to better spell out how they are currently being used by journals hosted at the [Centre for Digital Scholarship] at UNB Libraries. 

**It is important to note** that the DOI Plugin within OJS is not maintained or created by the development staff at the Centre for Digital Scholarship at UNB Libraries. The primary work is done by the development team at the [Public Knowledge Project] (PKP) and can be viewed directly on [Github]. You can find the code for the CrossRef Plugin [here](https://github.com/pkp/ojs/tree/master/plugins/importexport/crossref). 

##1.0 DOIs

###1.1 What is a DOI? 

DOI stands for **Digital Object Indentifier**... 

>"... meaning a "digital identifier of an object" rather than an "identifier of a digital object". The DOI system is designed to work over the Internet. A DOI name is permanently assigned to an object to provide a resolvable persistent network link to current information about that object, including where the object, or information about it, can be found on the Internet. While information about an object can change over time, its DOI name will not change. A DOI name can be resolved within the DOI system to values of one or more types of data relating to the object identified by that DOI name, such as a URL, an e-mail address, other identifiers and descriptive metadata." ([DOI Handbook], 2015)

DOIs are unique ids that can be applied to pretty much any object. For our purposes, we often talk about DOIs being assigned to *journal articles*. However, they can also be applied to data sets, images, research instruments, book reviews, or even whole issues of journals. The benefit – as hinted at in the quote above from doi.org – is that a DOI stays the same even if content moves around. Since a DOI never changes - and is resolvable through a URL - a DOI for an item will always lead a user to the place where that item resides. This is known as **persistent identification**. They also allow for better **citation tracking** and improved **article metrics**.

DOIs consist of two parts, a **prefix** and a **suffix**. For example: 

> 10.12345/suffix.for.the.doi.54321

In this case the **prefix** is 10.12345. Prefixes are usually assigned to a journal by the organization they have registered with. The **suffix** is often generated automatically by whatever system manages content. They are item-level idenfitiers. They *must be unique*. 

Also, DOIs allow for the possibility to link to any file with a registered URL. So, if a DOI has been registered, you can turn any DOI into a URL. You simply prepend the following...

> http://dx.doi.org/

... to your DOI. A complete link looks like so:

> http://dx.doi.org/10.12345/suffix.for.the.doi.54321

Any DOI you see can be located using this method, and some browsers now accept DOIs as direct links without the prepending of the dx.doi.org URL. 

###1.2 How can I get DOIs?

DOIs can be assigned to any object, but they are mostly useless unless they are registered with an organization who manages them. There are a number of these organizations and – mostly – they each have a different focus, associated cost, and submission process. 

- [mEDRA] // the multilingual European DOI Registration Agency. mEDRA utilize a paid service that is specific to publications or organizations in Europe. 
- [DataCite] // they focus primarily on applying DOIs to research datasets, research materials, and grey literature. DataCite is more of a research network, with emphasis on national or regional centres of management for DOIs, with an understanding that economic structures may vary. 
- [Zenodo] // developed in partnership with CERN, Zenodo is a free service that applies DOIs to anything falling within the mandate of "the long tail of science". This includes data, white papers, research data, source code from Github, as well as articles. It also serves as a general science repository, ideally for the sharing open sharing of research across all of science. 
- [CrossRef] // see directly below...  

###1.3 What is CrossRef?

![](http://www.crossref.org/images/citation_linking_graphic_24x106_white.png)

> CrossRef is an official Digital Object Identifier (DOI) Registration Agency of the International DOI Foundation. It was launched in early 2000 as a cooperative effort among publishers to enable persistent cross-publisher citation linking in online academic journals. CrossRef is the common name used by the Publishers International Linking Association (PILA). 

> CrossRef is also a not-for-profit association of about 2000 voting member publishers who represent 4300 societies and publishers, including both commercial and not-for-profit organizations. CrossRef includes publishers with varied business models, including those with both open access and subscription policies. CrossRef does not provide a database of fulltext scientific content. Rather, it facilitates the links between distributed content hosted at other sites.

> In addition to the DOI technology linking scholarly references, CrossRef enables a common linking contract among its participants. Members agree to assign DOIs to their current journal content and they also agree to link from the references of their content to other publishers' content. This reciprocity is an important component of what makes the system work. ([Wikipedia: CrossRef], 2015)

OJS has support for a number of DOI exporting functions. Though this guide is specific to CrossRef for the most part, further documentation is available from the [PKP Wiki DOI Plugins Documentation] page. 

####1.3.1 Registering with CrossRef

At the moment, the Centre for Digital Scholarship *does not offer CrossRef Sponsorship*. This means that in order to use the [CrossRef] service, your journal will need to become a member with the organization directly. Their "[Join CrossRef]" page has more information on what this entails.  You'll be asked to: 

- submit a membership agreement form
- submit an application form
- pay an annual fee ([Current Fee Schedule])
- pay a deposit fee for each submission ([Current Fee Schedule])

[CrossRef] offer other services as well, such as a metadata tool that can locate existing DOIs from pasted Reference/Works Cited data. They have tremendous and extensive documentation should you have any specific questions about their services. 

##2.0 OJS

###2.1 How do I configure OJS for DOIs?

The first step for OJS is to setup your DOI settings. You'll need to **enable** and **configure** the "DOI" public identifier plugin at: 

> **Journal Manager** > **System Plugins** > **Public Identifier Plugins** > **DOI Plugin**.

- click the **enable** link under the plugin title; 
- click the **settings** link under the plugin title once enabled
- configure the plugin... 

![](https://raw.githubusercontent.com/unb-libraries/journals-docs/master/images/doi01.png)

- Under the **Journal Content** section, please select *Articles*. You may also assign DOIs to *supplementary files* if you wish. Issues and galleys are not recommended. 
- Under **DOI Prefix** you must include a DOI prefix which you get from your DOI registration agency (ie: CrossRef). 
- Under **DOI Suffix** you must also configure the DOI suffix. We strongly recommend selecting the **use default patterns** setting if you are a new journal and have not previously had DOIs issued.
	- However, for more full control, or if you need more predictable DOI results for copyediting, feel free to select the last option about individual DOIs. Please note that you should take the utmost caution assigning these DOIs, however. 
- The final button on the page allows you to **Reassign DOIs**. Basically don't ever click this. Please. There's really no reason to unless you're just starting and it will cause a *not insignficant mess* if you've got DOIs already assigned. 

####2.1.1 How do I assign a DOI to an article? 

At any point after an article has entered the review process, a DOI can be assigned by an editor. This is done on the Metadata page for an individual article in OJS. There are a few ways to get to there:

- click on **User Home**
- click **Editor**
- find the relevant article either in **In Review** or **In Editing**
- click on the **Title of that article**
- click either the **Summary** or **Editing** subheadings
- click either the **Edit Metadata** or **Review Metadata** links, depending on which subheading you clicked before respectively
- scroll down to the DOI section and input only the suffix for that article into the field.
	- you may also opt to omit a DOI for a particular article if it doesn't need one by clicking the box next to "Exclude this article from assigning it a DOI"

![](https://raw.githubusercontent.com/unb-libraries/journals-docs/master/images/doi02.png)

####2.1.2 How do I submit or register DOIs?

OJS has numerous options for exporting DOIs for any of the major DOI registration organizations. You can view any of the options in OJS by navigating to:

> **Journal Manager** > **Import/Export Data** > select the export option that matches the organization of your choice.

For the purpose of this documentation, we're going to focus only on the CrossRef plugin. Again, for further information on configuring the other DOI plugins in OJS, please visit the [PKP Wiki DOI Plugins Documentation].

###2.2 How do I configure the CrossRef Plugin in OJS? 

As of version 2.4.5 of OJS – released in 2014 – OJS features a CrossRef plugin that allows users to **submit their DOIs directly from the OJS interface**. Other new features include:

- article-by-article DOI withdrawl for flagging articles that do not need DOIs
- article-by-article DOI clearing in case of a typo or other error
- automatic CrossRef submission on article publication
- ability to filter and submit to CrossRef "unregistered" content

The plugin comes with a few extra preliminary steps and assumes that you have *already registered with CrossRef*. 

1. Ensure that all Journal Setup steps that the CrossRef plugin requires have been filled in. Under **Journal Manager** > **Setup** > **1. Details** you will need the following fields filled out:
	- Journal Title
	- Journal Initials
	- Journal Abbreviation
	- Journal ISSN (or electronic ISSN)
	- Principal Contact (name and email)
	- Technical Support Contact (name and email)
	- Publisher (Institution and URL)
2. OJS must be configured for DOIs. See section **2.1** above. 
3. Ensure that your articles have DOIs assigned to them. See section **2.1.1** above. 

####2.2.1 Configuring the CrossRef Plugin

Navigate to the **CrossRef Export/Registration Plugin**:

> **Journal Manager** > **Import/Export Data** > **CrossRef Export/Registration Plugin**

1. Enter the name and email address of the depositor (the system will automatically fill in the name of your technical support contact).
2. Fill in your username and password data as assigned by CrossRef when you become a member.
3. Select whether or not DOI submission will occur automatically on publication of an issue (this is off by default, and probably recommended until you're confident your DOI workflow is consistent)

The system will tell you if configuration is complete on this page. 

###2.3 Submitting DOIs using the CrossRef Plugin

Navigate to the **CrossRef Export/Registration Plugin**:

> **Journal Manager** > **Import/Export Data** > **CrossRef Export/Registration Plugin**

Under the heading **Export Data** you'll have three options:

- Unregistered Articles // shows you a list of all articles in the system that haven't been submitted by this plugin specifically. 
- All Issues // shows you a list of all articles in the system that haven't been submitted or "marked as registered" by this plugin specifically. 
- All Articles // shows you a list identical to "Unregistered Articles" for some reason. Cool. 

If you've configured everything properly and you are lucky, you should be able to submit a DOI to CrossRef by clicking the **REGISTER** button to the right of a specific title. You can also click the relevant checkbox and click the Register button at the bottom of the page. 

When you first submit a DOI this way, it will have a notification pop up under the "Status" header that says "submitted". If you click a "submitted" link, OJS will ask you to login to your crossref backend with your CrossRef credentials. You'll be able to see an XML file that tells you the status of your DOI submission. 

> These submissions take time, so whether or not your submission was successful, it could be a while before you know what it's status is. Submissions remain in this queue with "Submitted" status until they are cleared by CrossRef. At the moment, it is unclear how OJS pings CrossRef servers for this information. One way to find out is to submit a DOI a second time. If it's been accepted entirely, it'll disappear from the list. 

##3.0 DOI's in Markup

Follow previous patterns for displaying DOIs in your detailed Markup. Any article from Atlantic Geology or Geoscience Canada from the last year should have an example of how we display those situations. It is well established.

DOIs in Detailed Markup need to be linked. This is actually a requirement of CrossRef. This means that the links are clickable and users can hop from one thing to the other. This is *only relevant in Atlantic Geology* for the time being. The process is pretty easy – the most important thing is that you understand that we are doing to wrap **every HTML link with dx.doi.org in it with a special tag**. We only want the DOI links. For this, we'll use regular expressions. 

The first part of this process is that all the URLs have to be one complete string from beginning to end. URLs cannot break across lines or have white spaces in them. For example, it's common for a URL to span two lines in the XML. It might not be obvious that it's happening, but it would look something like this:

```
http://dx.doi.org/10.12789/geocanj
.2013.40.015
```

This is problematic because that line break will be construed as a white space and the link won't work. This also happens with individual white spaces in URLs. For example:

```
http://dx.doi.org/10.12789 /geocanj.2013.40.015
```

In this case, there's a white space between the 9 and the /. These need to be shored up before we use our search and replace function. Once they are, you're ready to replace. 

You're going to want to put something like this in your search field:

```
http://dx\.doi\.org/(\S+)\.</alinea>
```

Let's talk about what's happening here. First of all, you'll notice a bunch of forward slash characters (\). These are escaping the periods you see in the URLs. This is because periods mean something in regular expressions and this safely skips over those for you. Secondly, you'll notice that the suffix part of the DOI has been replaced by **(\S+)**. This is a regular expression representing any non-whitespace characters between the dx.doi.org part of the URL and the period (and closing ``</alinea>``) at the very end that your reference ends with. 

We're going to replace this with the following:

```
<liensimple id="li" xlink:href="http://dx.doi.org/$1">http://dx.doi.org/$1</liensimple>.</alinea>
```

So, here, we've added in the ``<liensimple>`` (simple link) tag that we need for linking a URL in the XML file. It has it's own unique ID that will be enumerated by the **cleanUp** script. You'll also notice the **$1**, which represents the content we took out with the **(\S+)** earlier. The URL is repeated twice, once as the URL for where the link goes, and the other time as the original text to link. 

The final, replaced version should look like this:

```
<liensimple id="li3" xlink:href="http://dx.doi.org/10.12789/geocanj.2013.40.015">http://dx.doi.org/10.12789/geocanj.2013.40.015</liensimple>
```

<hr><!--footnotes-->

[Centre for Digital Scholarship]: https://digitalscholarship.lib.unb.ca/journal-publication-services
[CrossRef]: http://crossref.org
[Current Fee Schedule]: http://www.crossref.org/02publishers/20pub_fees.html
[DataCite]: https://www.datacite.org/
[DOI Handbook]: http://www.doi.org/doi_handbook/1_Introduction.html
[Github]: http://github.com
[Join CrossRef]: http://www.crossref.org/01company/join_crossref.html
[mEDRA]: https://www.medra.org/
[Open Journal Systems]: https://pkp.sfu.ca/ojs/
[PKP Wiki]: http://pkp.sfu.ca/wiki/index.php?title=Special%3ASearch&search=doi&go=Go
[PKP Wiki DOI Plugins Documentation]: http://pkp.sfu.ca/wiki/index.php/DOIPluginsDocumentation#Manual_Metadata_Import_to_Crossref
[Public Knowledge Project]: http://pkp.sfu.ca
[Wikipedia]: http://en.wikipedia.org/wiki/Digital_object_identifier
[Wikipedia: CrossRef]: http://en.wikipedia.org/wiki/CrossRef
[Zenodo]: https://zenodo.org/