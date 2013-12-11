# Crossref, OJS, and DOIs 

# Introduction
Digital Object Identifiers (DOIs) are unique ids applied to digital items (files, sites, documents) that allow for persistent linking to that online item. Since a DOI never changes - and is resolvable through a URL - a DOI for an item will always lead a user to the place where that item resides. In terms of our use of Open Journal Systems (OJS) here at UNB, a DOI can be assigned to the following:

- journals
- journal issues
- individual journal articles
- individual journal *galleys* (wherein the PDF and HTML galley have separate DOIs)
- supplementary files 

> *Typically, DOIs are only assigned to individual articles.*

DOIs allow for easy linking to citations across publishers and organizations. They are increasingly common in academic journal publication, particularly with the sciences. They also allow journals to - with the help of DOI registration agencies - provide important metrics regarding individual publications. That said, a DOI by itself is fairly useless if it has not been registered with a DOI registration agency. 

# DOI Registration Agencies
There are a number of DOI registration agencies depending on geography or publication focus. For the purposes of our installation of OJS, the only registration agency that matters is [Crossref](http://www.crossref.org/). This is because Crossref is considered to be the official link registration service for scholarly and professional publications. Crossref have [extensive documentation](http://help.crossref.org/#home) if you should be in the unenviable position of having to sort out a Crossref problem. You can also [email their support line](http://crossref.zendesk.com/anonymous_requests/new) and they will pretty quickly help you out. They're nice, in my limited experience. 

# How it works
Here's a DOI from [Atlantic Geology](http://journals.hil.unb.ca/index.php/ag/index):

10.4138/atlgeol.2013.001 

DOIs are broken into two distinct parts, **prefix** and **suffix**. A prefix for a DOI is static. A journal might have their own, or a publisher might have their own. This part of the DOI never changes. Take, for example, the DOI for Atlantic Geology: 

10.4138

This part of their DOIs will always be the same. However, the second part will change for every article, and will be unique to that article (it won't be found anywhere else in our install of OJS). 

atlgeol.2013.001

DOIs allow for the possibility to link to any file with a *registered* URL. So, if a DOI has been registered with Crossref, you can turn any DOI into a URL. You simply prepend the following... 

http://dx.doi.org/

... to your DOI. A complete link looks like so:

[http://dx.doi.org/10.4138/atlgeol.2013.001](http://dx.doi.org/10.4138/atlgeol.2013.001)

**The idea** is that if you change the placement or filepath of the file, you can update that URL with Crossref and the DOI will still always take users to the article. It becomes a persistent way to link out to the content. *That is valuable for lots of reasons I won't bother going into here*.

# Workflow
Our workflow for DOIs is pretty straight-forward. Since we only have two journals that use it and these journals are both geology journals AND these journals both have unique publication methods (one publishes their content iteratively and the other publishes with pre-prints and finished copies), this is a good thing. 

> *I should point out that there's a good chance this workflow will change and probably a good chance that it will change within the next year thanks to OJS updates and a changing relationship between PKP and Crossref.*

## Assigning a DOI in OJS.
This is done on the Metadata page for an individual article in OJS.  There are a few ways to get to there.

- **User Home**
- **Editor** for the relevant journal
- Find the article either in **In Review** or **In Editing**
- Click on the **Title** of that article
- Click either the **Summary** or **Editing** subheadings
- Click either the **Edit Metadata** or **Review Metadata** links
- Scroll down to the DOI section and *input only the suffix* for that article into the field. 

> *This is a unique situation, because for our two journals, our editors will actually mostly be doing this themselves. It is your job, however, to make sure that content isn't published with that DOI field left blank. If it is, that might be problematic. Stay vigilant!* 

## Updating the Public ID for the Issue that DOI is in. 
Once the issue is published (or if it is a **Future Issue**), you may want to (as **Editor**) go into the issue and enter the suffixes as the "public_ID" for relevant articles. This changes part of the URL in OJS to have the DOI prefix and suffix included.

> *This isn't strictly necessary for any real reason, but we seem to do it regardless. 

## In Markup
Follow previous patterns for displaying DOIs in your detailed Markup. Any article from Atlantic Geology or Geoscience Canada from the last year should have an example of how we display those situations. It is well established.

### Linking DOIs in Detailed Markup
*This requires a regular expression and craftiness... stay tuned.*

So, DOIs in Detailed Markup need to be linked. This is actually a requirement of Crossref. This means that the links are clickable and users can hop from one thing to the other. This is *only relevant in Atlantic Geology* for the time being. The process is pretty easy – the most important thing is that you understand that we are doing to wrap **every HTML link with dx.doi.org in it with a special tag**. We only want the DOI links. For this, we'll use regular expressions. 

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

## Submitting a DOI to Crossref // XML Export
As I mentioned earlier, DOIs need to be **registered** to be of any use to anyone. Putting `http://dx.doi.org/` in front of your DOI will not create a link if the DOI hasn't been registered. Any journal we work with is on the hook for having their own DOI account and prefix. 

Registering a DOI is, currently, a three-stop process. It starts once an article with a DOI has been published. It's like this:

### 1 // Crossref XML Export
OJS can export metadata in the Crossref metadata standard for you. Do this:

- **User Home**
- **Journal Manager**
- **System Plugins**
- **Import/Export Plugins**
- Crossref XML Export Plugin (Click on "**Import/Export Data**" Link directly below)
- Select **Issue** or **Article** Export, depending on what you're up to. 
- Check off the boxes for what you're exporting, click on **Export** below. 
- Save to whatever directory. 

### 2 // Checking the validity of the Crossref XML
The XML might need adjusting. This happens occasionally. It's usually not a big deal. Open up the XML in Oxygen or any other editor that does validation. If something is wrong, check it out. It's possible that you might have to cull some unnecessary elements (you'll know because they have giant red lines under them). 

> *For example: right now, there's a bug where OJS is adding slots for supplementary files to have metadata and DOIs in the Crossref Export. This is inappropriate, because our journals don't actually even have DOIs for their supplementary files. When you make the file currently (like, November 2013), there will be an element called `<component_list>` that is showing as invalid. You can delete it entirely, because we're not submitting these to Crossref. This is just one example of the sort of thing you might see in this situation. 

### 3 // Submission to Crossref. 
Right now, we have to do this manually. It's possible that journal editors might also be able to do this if they are *in the mood*. There is talk that OJS may be able to do this on it's own sooner than later. It's pretty straight forward. 

- Go to  [Crossref's backend](http://doi.crossref.org/servlet/useragent) for submission. 
- Login as the Required Journal
- Click the "Submissions" tab
- Click "Choose File" and select your *valid* crossref.xml file
- Make sure that the "type" is set to "Metadata"
- Click "upload" 

And that's it. Shortly thereafter, James (probably) will get an email saying whether or not the upload was a success. If it was, you're all set! If not, you'll have to resubmit after sorting out why the upload failed. 

**And that's it!**

# Addendum
## Cost
You should now that submitting a DOI for registration costs a journal $1 per thing you upload. You might be initially concerned that messing up will cost the money, but resubmissions don't cost anything. Back-issue uploads cost $0.15 per article. It is unlikely that you will see this, but it's important. 

## Moved Content
Should a file have to move to a new URL for any reason, the DOI will have to be updated with Crossref. You can do this by resubmitting it. Editors should be made aware of this fact as well. 