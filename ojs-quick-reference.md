#OJS Quick-Reference Guide: Open Journal Systems 2.4.2
Written by: Michael Nason, August 9, 2012
Updated by: Michael Nason, November 22, 2013

The following instructions are to serve as a quick-reference guide to Open Journal Systems version 2.4.2. These instructions will not so much explain the ‘why’ of things, but will give you an understanding on how to quickly:

 - set up a journal;
 - create users;
 - assign roles;
 - submit manuscripts;
 - run manuscripts through peer review and editing phases;
 - schedule and publish an issue.

For more in-depth instruction on any OJS issue, please use the following resources:

- PKP [Wiki](http://pkp.sfu.ca/wiki/index.php?title=Main_Page)
- PKP [Support Forum](http://pkp.sfu.ca/support/forum/)
- PKP [School](http://pkpschool.sfu.ca/)
- OJS [Documentation Page](http://pkp.sfu.ca/ojs/ojs_documentation/)
- Online context-sensitive help, available as a “**Journal Help**” link in the upper-right corner of any OJS page.
- And of course, always feel free to email us with any questions you may have.

#I. JOURNAL SETUP

In order to set up a journal, you must be *logged in* and *enrolled* as a **Journal Manager**. If you click on **User Home** at the top of any page and see Journal Manager listed under your roles, than you are already enrolled as one. If you are not but should be, please contact the ETC so that the System Administrator can help you.

There is a 5-step journal setup process. You can return to edit these options at any time.

To reach the main journal setup section, click the following links (“User Home” is always at the top of the page, and you will be frequently clicking it):

> User Home > Journal Manager > Setup

You will see the following 5 steps laid out:

- Details
- Policies
- Submissions
- Management
- The Look

Click on **Step 1: “Details”** and fill out all information possible, keeping in mind the following notes:

- Make sure any field with an ‘*’ is filled out, as they are mandatory.
- There are two options for inputting an ISSN: Print and Online. If you have had a print run before, you should already have a print ISSN. *If you need assistance in obtaining an online ISSN, please contact the ETC*.
- **DOI Prefix and Suffix information** is only relevant if your journal is registered with a company like **Crossref**. DOIs (Digital Object Identifiers) are unique IDs assigned to every article or issue you publish and are uploaded to a cross-referencing service. A DOI ensures that your articles are always available by searching for their unique ID.
- Choose **Principal Contact** carefully, as their email address will be associated with most outgoing email.
- Technical Support Contact should be someone at the ETC, typically James Kerr. James’ information is as follows:

> James Kerr
> jkerr@unb.ca
> (506) 447-3453

- You can edit your outgoing email signature in section 1.4. This signature appears on every system email sent out by OJS. You may choose to put the Technical Support Contact information in the signature.
- You can also add a Bounce Address. This email address will receive notification any time a system email is returned as undeliverable. You may choose to put the Technical Support Contact email address here.
- Section 1.8, Search Engine Indexing, is important to sites like Google and Yahoo and should be filled out. Keep Keywords as specific as possible, ie. for Atlantic Geology keywords like “Nova Scotia; New Brunswick; Prince Edward Island; Newfoundland; Labrador; geology; igneous; metamorphic; structural geology; marine geology; paleontology; sedimentology; petroleum geology; geophysics” would work well.

Click on “Save and Continue”. When you reach the next page, click Either **2. Policies** or **Next Page**. Fill out all information possible, keeping in mind the following notes:

- Box forms on this page can accept limited HTML code. You can enclose words in HTML tags to change their appearance:

```
<i>Italic</i>
<b>Bold</b>
<u>Underline</u>
```

And so on…

- There is an unclear distinction between **Peer Review Policy** and **Review Guidelines**. Peer Review Policy appears in About the Journal, and as such should be a short outline detailing your review policy. Review Guidelines are your complete guidelines and/or a checklist, viewable by reviewers during the review process.
- There is a default **privacy statement** that you may wish to change.
- In Section 2.5, you can add extra items to appear in the **About the Journal** page. You can add as many extra sections as you require.
- There is a default **Open Access policy** that you may wish to change or remove.
- At the current time, please ignore section 2.6 Journal.
- Section 2.7 **Potential Reviewer Database**, is linking your reviewer selections to an externally hosted database. Since we are not currently providing this service with our own journals, you can likely ignore this section.

Click on “Save and Continue”. When you reach the next page, click Either **3. Submissions** or **Next Page**. Fill out all information possible, keeping in mind the following notes:

- The large fields on this page can accept limited HTML code. You can enclose words in the HTML tags mentioned above to change their appearance.
- There are default **Author Guidelines** that you may wish to change.
- There is a default submission checklist that you may wish to edit. Feel free to add or remove items. These items will appear in the author submission process, and authors will have to check off every item on this list before submitting a manuscript.
- Section 3.2 has a default **Copyright Notice** that you may wish to change.
- Section 3.3 allows you to define a **Competing Interests** policy if your journal requires authors to submit one.
- Section 3.4 allows you to set fields where authors can index their work. If checked, these will appear in the article submission process. You will always be able to edit author-submitted material at a later date.
- At the current time, please ignore Step 3.5 Register Journal for Indexing.
- Section 3.6 allows you to enter an email so that new submissions will prompt an email from the system for notification.

Click on “Save and Continue”. When you reach the next page, click Either **4. Management** or **Next Page**. Fill out all information possible, keeping in mind the following notes:

- Box forms on this page can accept limited HTML code. You can enclose words in the above HTML tags to change their appearance.
- If your journal is Open Access, you may wish to change the Open Access Policy.
- If you are planning on restricting article access to paying subscribers, make sure you choose option 2 (The journal will require subscriptions to access some or all of its contents) in section 4.1.
- Under User Registration you can control how users register with your system. By default, users can register as both readers and authors, but you may wish to provide less access; you may also wish to allow users to register as reviewers. Additionally, if you like, the journal manager can manage all user registration manually.
- If you wish to fast-track article submissions and not use the OJS system for keeping track of Copyeditors, Layout Editors and Proofreaders, please ensure that the option 2 (responsibility is undertaken by the editors) is selected under Sections 4.5, 4.6 and 4.7.

Click on “Save and Continue”. When you reach the next page, click Either **5. The Look** or **Next Page**. Fill out all information possible, keeping in mind the following notes:

- The ETC will typically handle any graphical responsibilities for your journal. If you wish to take on more responsibility, please take a look at the following [documentation](http://pkp.sfu.ca/files/CustomizingOJS.pdf)
- You can modify what appears on the Journal main page by editing “Journal Description” and “Additional Content”. HTML tags can be used.
- Feel free to add information to the Journal Footer section. This information will appear on most pages of your journal.

#II. MANAGING USERS

You must be logged in as a **Journal Manager** to add, edit and delete users and assign roles. Typically, people reading your site can register as **Readers** and **Authors**. You can also allow an option for them to register as **Reviewers**.

The following are the only roles you will normally have to worry about:

- Readers receive email notification of new issues.
- Authors can submit to the journal.
- Editors have administrative control over the publishing process.
- Journal Managers have administrative control over the entire journal.

Visitors to the site can register by clicking the **Register** link at the very top of the web page. This link disappears when a user logs in.

Occasionally, a user may already exist in the OJS system as a whole, but may not officially be enrolled with your journal. To view, edit and remove all users enrolled with your journal, go to

> User Home > Journal Manager > Users Enrolled in this Journal

Here you will find a list of all users enrolled with your journal. If you click on the **Edit** button to the right of a user's name, you will be taken to a page where you can edit any information except their username. If you click on the **Log in As** button, you will be able to view the journal as that user (please note: if the user is enrolled in another journal within our system, this option may not be available to you). If you click on the **Remove** button, you will unenroll the user from your journal completely. If you click the **Disable** button, you will disable the user from the system as a whole. Please do not disable a user without first consulting the ETC.

To add a new user to your journal, please follow these two steps:

1 // Check to see if the user already exists within the OJS system as a whole. Go to:

> User Home > Journal Manager > Enroll a User from this Site in this Journal

At the very bottom of the page you will find a link that says **Enroll Existing User**. This will take you to a listing of all OJS users. At the very top of the listing you will have a search field. Search for the new user's email address, making sure to drop down the first search field and select **Email**. If the search returns no results, they do not exist within the OJS system and you will have to create the user from scratch.

2 // To create a new user, go to:

> User Home > Journal Manager > Create New User

And fill out the Create New User form. There are a few special options to keep in mind when creating a new user from scratch.

- You must fill in all form fields that have an asterisk: Username, Password/Repeat Password, First Name, Last Name, and Email.
- While you are not explicitly bound to any naming convention for a person's username, we typically keep to first initial + last name; so, James MacGregor would be jmacgregor, and so on.
- You can highlight multiple roles under the **Enroll user as** option by clicking on one role, pressing and holding Ctrl on your keyboard, and clicking on other roles to highlight them; this is handy if you want to enroll a user as both an author and an editor, for example.
- In order to keep track of users within your journal system, it is highly recommended that you assign at least the role of reader. Otherwise, they are enrolled within the system but not particularly attached to your journal.
- You can have the system generate a random password and email the new user with their username and password once registration is complete; this is the most secure option.
- If you are registering multiple users, there is a convenient **Save and Create Another** button at the very bottom of the form.

## Logging in as another user

If you are assigned the role of Journal Manager for your journal, you may **log in as** any users of your journal so long as they are not enrolled in any other journals on our system. Logging in as a user can be helpful for troubleshooting or walking new users (editors, reviewers, authors… etc.) through the system. If you need to **log in as** a user:

- Go to **User Home**.
- Click on **Users Enrolled in this Journal**.
- Find the user you’re looking to enroll as, and look to the links on the right. Click on **Log in as**.

If, at any point, you wish to go back to your existing user, look to the sidebar under the header **USER** and click the option **Log out as user**.

#III. AUTHOR SUBMISSION

In order to submit an article, you must be registered as an author. If you click on “User Home” at the top of the site and see an Author option listed under your roles, then you are already registered. If you are not, please contact a Journal Manager to add you. If you are a Journal Manager, you can follow the steps in II. MANAGING USERS to edit a user’s account.

The article submission process has 5 steps. To start a submission, go to

> User Home > Author

And click on **Step one of the submission process** at the bottom of the page.

## Step 1. Starting the Submission

Step 1 is essentially an agreement form. You will have to check off a checklist, and possibly agree to a copyright notice, depending on how the Journal Manager set the journal up. You may also have to choose which journal section your article falls under. Finally, you have the option of including comments to the editor. Once step 1 has been completed, click **Save and Continue**. The system will not let you proceed if you are missing a step.

Please note that once you click save and continue the system stores your submission. You can revisit and edit it at any time along this process by going to:

> User Home > Author

From here you can view a list of active submissions.

## Step 2. Enter Metadata

Step 2 is where you upload and enter metadata about your submission: Authors, Title, Abstract, etc.

Although step 2 comes up with your name as the author by default, you may be acting on behalf of another author and may wish to change the Author name. You may add more than one author by clicking the “Add Author” button. If you have more than one author listed, you can reorder authors as listed in your citation by pressing up and down arrows; you can also designate which author is the primary email contact by clicking on a radio button.

You must also include your article title, and may include an abstract if appropriate. The Journal Manager may also have opted to allow authors to provide their own indexing information and keywords, in which case you will see fields for that information. This information is not mandatory, and editors will have the option to edit this information at a later date.

## Step 3. Upload

OJS will prompt you to select the file you wish to upload. Follow the instructions on the screen to properly upload your files. If the journal has requested Blind Review, clicking on the link **Ensure Blind Review** will inform the user on how to properly prepare their file for blind review using common software.

Please note: if you do not click **upload** after selecting your file, it will not upload. Failure to upload at this step will result in the absence of your content within OJS. The system does not allow you to upload your content at a later time.

## Step 4. Upload Supplementary Files

Step 4 is where you can upload supplementary files and enter metadata. Like articles, there are many fields you can enter, but very few of them are requirements.

## Step 5. Finish

Step 5 is the last step of the process. If you only have an author roll in OJS then you’re process is finished. It’s worth noting, however, that if you’re an editor or journal manager then you have an option on this last page to click a link that moves the content directly to the last stage of the review process. This is convenient if you’re submitting content that’s already been accepted but outside of the review process.

# IV. PEER-REVIEW / MANAGING USER SUBMISSIONS

In order to manage user submissions, you must be enrolled as an editor. If you click on **User Home** at the top of the site and see an Editor option listed under your roles, then you are already enrolled as one. If you are not, please contact a Journal Manager to add you. If you are a Journal Manager, you can follow the steps in **II. JOURNAL MANAGEMENT** to edit a user’s account.

To manage submitted manuscripts, go to

> User Home > Editor

You will see a heading titled Submissions, underneath of which will be the following ordered list:

>    Unassigned (x)
>    In Review (x)
>    In Editing (x)
>    Archives

Where x is the number of submissions currently at that stage. What you will now be doing is moving article manuscripts from one stage to the next.

## Step 1. Unassigned

There should be a number of manuscripts in the Unassigned section. Click **Unassigned**. You will now see a listing of all newly-submitted manuscripts.

These manuscripts need to have an editor assigned to them. To do this, click on the manuscript title; you will be brought to a summary page for that manuscript.

On the summary page, note that you can email the author by clicking the email icon next to their name; you can add a supplementary file; you can change which section this article is assigned to; and you can also edit the author’s contributed metadata.

There is also an Editors heading. Under the Editors heading, you will see options to add Section Editor, add Editor, or add Self. You must add an editor at this stage before the manuscript can proceed to the next step. If you add an editor besides yourself, the system will ask if you’d like to send them an email. You must click either **Send** or **Skip Email** to assign that particular editor.

The editor you add essentially takes responsibility for this manuscript. After you add an editor, you can always replace them.

## Step 2. In Review

You can now go to:

> User Home > Editor

And see that an article has moved to the **In Review** pile. To view, click:

> In Review > Article Title

You are now on the manuscript review page. The first step you need to accomplish is assigning a review copy. If the author uploaded a manuscript during the submission process, you can designate that original file as the Review version by checking a box and clicking Record; you can also upload a revised copy if you’d like (if you had to remove identifying marks, if the author sent you a new version, etc.). Once this is done, you’ll see the Review Version has been created. The file name will change to xxxx-xxxx-x-RV.doc.

The next step is to assign a reviewer. On the same page, click **Select Reviewer**. You will be presented with a list of reviewers to choose from. Click **Assign** next to your reviewer of choice. You will return to the Submission Review page. Scroll down to Reviewers. Where it says **Reviewer A** you will see an email icon, next to your reviewer’s name. Click the icon and choose either **Send** or **Skip Email** in order to proceed to the next step. Once this is accomplished, the reviewer can now log in by going to:

> User Home > Reviewer

And commit actions on the article.

## Step 3. Review Submission

In order to review submissions, you must be enrolled as a reviewer. If you click on **User Home** at the top of the site and see a Reviewer option listed under your roles, then you are already enrolled as one. If you are not, please contact a Journal Manager to add you. If you are a Journal Manager, you can follow the steps in STEP **2: JOURNAL MANAGEMENT** to edit a user’s account.

To begin the article review process, go to:

> User Home > Reviewer

where you will see a list of review requests. If you have a waiting review request, click on the article title link. You will be taken to a page that has some information about the article to be reviewed, and a series of steps to follow.

Please follow these review steps:
1. You must click on the email icon beside either “Will do the review” or “Unable to do the review”, of course depending on whether you will do the review or not. You cannot proceed further before notifying the editor of your decision. Clicking on either email icon will bring up an email template; you must click either “Send” or “Skip Email” to confirm the action.
2. You can now download the review version of the manuscript.
3. Click on the note icon to fill out your review. You will have the opportunity to write comments both for the editor and author to see, and for the editor only. You will not be able to select a recommendation until you comment. Please note that until you select your final recommendation, you can come back to this note page and edit your comments. As soon as you select your recommendation, this page is locked to you.
4. You can optionally upload an edited review copy to the system here.
5. You can now select your recommendation. Again, you must either click “Send” or “Skip Email” to commit this action.

## Step 4. Back to In Review

The assigned editor will now have received an email notifying them of the finished review (provided the “Skip Email” button wasn't pushed, that is), and must now log in and move the manuscript forward. As an editor, go to

> User Home > Editor > In Review

And you will see your list of submissions in review, with ask/due/done dates beside them. Click on the title of a manuscript with a completed review. Under “Reviewer A” you will be able to click on an email icon to acknowledge the reviewer's response. You will also be able to click on a note icon to read the reviewer's comments, as well as click an option that allows the author to see the reviewer’s version of the document. If you wish, you can also assign another reviewer and go through this process again.

Finally, you can record an Editor Decision. Depending on what you choose here, several things happen. You can send the manuscript back for review, you can request revisions, you can decline the submission (in which case the manuscript will be taken out of queue and archived) and you can accept the submission for publication.

Choose your decision, and click “Record Decision”.

Emailing the author is not mandatory here, but it would be useful. If you've requested a new revision from an author, you must wait until the author has uploaded their revised version for it to appear here; you also have the option of uploading your own revised version, or going with the version that came back from review (known as xxxx-xxxx-1-ED.doc). Whichever you choose, make sure that the radio button next to it has been clicked, and send it to Copyediting in editing by clicking the “Send” button.

## Step 5. In Editing

By clicking the above button you will be automatically sent to the next Editing step. You can also go to:

> User Home > Editor > In Editing (x)

to see a list of articles ready for the editing process; x is the number of articles at this stage.

When you are “In Editing” click on a manuscript title to go to its editing page. You will see options to request Copyediting, Layout and Proofreading. Most journals are currently ignoring most of these steps and completing all copyediting and proofreading in-house, so for this version of the how-to we will skip both the copyediting and proofreading process. If you would like to experiment with these steps, however, by all means do so. It's not much different from the review request/workflow steps above.

What you do need to do is upload your final galley, one way or another. Depending on your contract with the ETC and your use of layout editors, there are two common methods to this.

## Method 1. Manually Email the ETC

Method 1 is the most common: once you have a manuscript that you are completely happy with, email it as an attachment to the ETC. It can be in almost any format, but please make sure it is a final galley. We can handle PDF fine. We will take this final file, create XML, HTML, and/or PDF files depending on your contract with us, and upload them as galleys for you. We can then schedule publishing the issue for you.


## Method 2. Uploading a Galley yourself

If you would like to tackle this job yourself (or would just like to know how we do it) follow these steps:

1. Go to: User Home –> Editor –> In Editing –> article title
2. Scroll down to Layout section. Under **Upload file to**, click the **Galley** radio button.
3. Click the **Browse** button, and find your galley file. The galley file can be either HTML or PDF. Once you find the file, click **Upload**.
4. You will be brought to a Galley information page; if the info looks correct, click **Save**. You can repeat this process if you have more than one file; for example, if you have both an HTML and a PDF file, or if a large article is split into two smaller files.
5. Once you are happy that you have all galley files in place, Click the **Send** button at the very bottom of the page to send the submission to scheduling.

# V. SCHEDULING

Now we may proceed to scheduling articles and publishing an issue. Go to:

> User Home > Editor > In Editing (x)

where x is the number of articles awaiting scheduling or subject to copyediting and laybout (again, you'll notice this number change as you move articles along the submission process).

Click on the **editing** link at the top of the page. About halfway down the page you’ll see a dropdown menu that says Scheduling. The list shows every available issue to schedule the article for.
Creating Issues

If you choose to schedule articles with already-published issues (either by choosing the current issue or one of the back-issues) the article will automatically appear with that issue.

To create an issue, go to:

> User home > Editor > Create Issues

On the Create Issue page you will be given the option of setting issue metadata (Vol., Number, Special Title, etc.) and adding a description that will appear with the Table of Contents. This page should come up with reasonable defaults, but please double-check that the Volume, Number and Year information is correct.

If subscription management has been enabled in the **Journal Setup** section (Section 4.3), and if you have not set a default subscription expiry date (see **Section 6. Subscriptions**, below) you will now have an option on setting default restrictions at the issue level. Under **Access** you can choose either **Open Access** or **Subscription** from a drop-down menu. You can then choose a date when the issue becomes open to all – so if you were to institute a 2-year moving wall, you would set that date for two years after you publish the issue.

When you're happy with the information here, click **Save** at the bottom of the page. You will be brought back to the scheduling queue; if you have scheduled all of your articles, the queue will be empty.

Now you can click on **Future Issues** on that page, or go to

> User home > Editor > Future Issues

where you will see an issue ready to be published. Click lick on the issue name to go to the issue page. Here you can order sections and article order by pushing up and down arrows. You can also change whether individual articles are subscriber-only or not. You can also click **Preview Issue** to see what it will look like when it is published, and you can click on **Issue Data** to change the information you just inputted above.

When you are satisfied with how your issue looks, click the **Publish Issue** button and then **OK** on the warning box. The issue will now appear under **Current** at the top of your site.

When you’re scheduling publication, you can assign articles to **Future Issues** so that you may assemble an issue before it’s ready for publication.

# VI. SUBSCRIPTIONS

OJS comes with built-in subscription management. At the moment, it does not include options for collecting subscription payments via Paypal or credit card, although there is plugin support for Beanstream for UNB-based journals.

If you turn on subscription management, you will be able to restrict access to some or all of your journal article content. To restrict content to the journal site itself, please contact ETC staff or check out **Step 4.1 Access and Security Settings** of the Setup Process (covered in Part 1 of this document).

## Enabling Subscription Management

To enable subscription management, you must be enrolled as a Journal Manager. If you are not enrolled as a Journal Manager, please contact the ETC or your Journal Head. If you are enrolled and logged in as Journal Manager, go to:

> User Home > Journal Manager > Setup

and click on “Step 4: Management”. Scroll down to “4.1 Access and Security Settings” and make sure that radio button 2 (The journal will require subscriptions to access some or all of its contents) is checked. Scroll to the bottom of the page and click “Save”.

Now go to:

> User Home > Journal Manager > Subscriptions

to access subscription options.

## Creating Subscription Types

You'll first want to create subscription types, such as Individual/Institutional, or location-based (Canada, US, International, etc.). Here is an example list of subscription types, taking into account individual vs. institutional subscriptions, as well as geographic location:

> Individual, In Canada 25.00 (CAD)
> Individual, International 30.00 (CAD)
> Institutional, In Canada 75.00 (CAD)
> Institutional, International 80.00 (CAD)

You can create as many subscription types as you wish.

To create a subscription type, go to:

> User Home > Journal Manager > Subscriptions

and click on “Subscription Types”. At the bottom of that page, click on “Create New Subscription Type”.

Create a name for the subscription type (see above for examples), and a description if you wish.

Enter the subscription cost, and choose the currency.

You can also add a default duration, for example “12” for one year.

Choose the format, or in other words, what the subscriber is granted access to (Print, Online, or both).

Choose whether subscribers should be validated via IP or domain authentication. If you leave this unchecked, the subscriber will have to log in with their username and password. If you check it, they will have to provide you with their IP addresses. This is useful for institutions who wish to grant access to a wider group of people (libraries, for example).

If you require subscribers to be part of an organization, check the next box.

If wish the subscription type to be secret, check the very last box.

Click **Save**, or **Save and Create Another** if you wish to create another subscription type.

## Adding Subscribers

To add a subscriber, take the following steps:

Go to:

> User Home > Journal Manager > Subscriptions

At the very bottom of the page, click on the link **Create New Subscription**. You will be presented with a list of users that have been enrolled in the OJS system.

To find a user, either use the search box at the top of the page, or browse page-by-page following the forward/next buttons at the bottom of the page. When you find them, click the **Enroll** button to the right of their name. You will be brought to a **Create New Subscription** page.

On that page you will have to choose a subscription type as defined in the above steps, and to choose when the subscriptions starts and ends. You will also be asked whether you would like a notification email to be sent, which is often a good idea for record-keeping. Finally, if you wish the user to be validated via IP address or domain, you must enter the proper IP addresses.

## Managing other Subscription Policies

To access other Subscription options, go to

> User Home > Journal Manager > Subscriptions

And click on the “Subscription Policies” link. Here you can fill out Subscription Manager information (this provides a contact address in the “About the Journal page) and publicly readable subscription information. You can also set subscription expiry reminders to be emailed, and detail open access issues. If you set a subscription expiry date, this overrides the option to set an expiry date on a per-issue basis during the journal publishing process.

# APPENDIX I: FREQUENTLY ASKED QUESTIONS

## FOR USERS

***How do I register myself as a user?***

If the journal allows outside registration, you can click the “Register” link at the top of any page. Once you have registered, you can click the “Log in” link at the top of any page, where you will be prompted for your username and password.

***I lost my password – how do I log in?***

If you've somehow lost your password, or if a Journal Manager has enrolled you as a user but has not emailed you your password, you can request a new one from the system itself. Click the “Log in” link, at the top of any page, and then click the “Forgot your password?” link on the page that comes up. You will be prompted for your email address, and the system will send you an email with a new password.

***How do I change my password / other user information?***

If you are not already logged in, you must click the “Log in” link at the top of any page, log in with your current username and password, and then click “Edit profile”. If you are logged in already, you can click

>User home > Edit my Profile

Or click “My Profile” on the right sidebar.

***Why do some images look small?***

Some internet browsers (IE, Firefox) will shrink displayed images to fit the browser window. If you’re looking at a figure in an article within OJS and you notice that your cursor changes to a magnifying glass when you mouse-over the image, clicking will increase the image to it’s regular size.

## FOR EDITORS

***Why are there old, outdated, or duplicate journal sections listed for my journal?***

You may notice that under

> User Home > Journal Manager > Journal Sections

you have several sections listed that may have been used in the past, but aren't in use any more. 99% of the time this is because the journal has a large number of archives uploaded to the system, and these sections need to be kept for archival/database purposes.

You can limit which sections are author-submittable by clicking on the “Edit” button next to a section title, checking the box beside “Items can only be submitted by Editors and Section Editors”, and clicking “Save”.

Also, you may come across duplicate sections, with or without typos. This is most likely the result of the ETC's archiving method. Please do not try to fix this yourself by deleting sections – rather, notify the ETC of any redundancies, and we will fix the issue.

## FOR JOURNAL MANAGERS

***How do I edit the emails that the system sends out?***

OJS has a number of email templates for various system actions, such as submission acknowledgement, subscription notification, etc. Many of these emails are sent out with the Primary Contact's name and email address used as the sender. While you can't necessarily edit this, you can edit what the email says. Go to:

> User Home > Journal Manager > Prepared Emails

where you will see a list of email templates. Find the email you would like to edit, click the “Edit” button next to it, and change the subject line and body to your satisfaction. Please note that anything within curly brackets ({}) references dynamically-generated content, such as Editor names, mailing addresses, etc. You can delete these lines if you want to.

You can also disable emails from this page, so that no email is sent when said action occurs.

***How do I add information or text to the homepage?***

There are a handful of different ways to add additional information to the homepage.

If you want to add information that remains fairly consistent over time go to:

> User Home > Journal Manager > Setup

and choose Step 5: The Look. Scroll down to “5.2 Journal Homepage Content”.

There is a Journal Description box that can take a small amount of descriptive text (HTML is allowed); this text will appear under the main homepage header.

There is an option to upload a homepage image. You can upload recent cover images etc. in this fashion.

There is a checkbox if you wish to have your current issue's table of contents displayed on the home page.

There is a box for Additional Content, which accepts HTML tags as well. You can have more text here. Any text entered in the Additional Content box will be displayed underneath the above content, if used.

If you want to add updated/updateable information, such as news and announcements, to your homepage go to:

> User Home > Journal Manager > Setup

and choose Step 4: Management. Go to 4.4 Announcements and check off the first checkbox to enable announcements. This will add an Announcements link to the top navigation bar. To add the announcements to the homepage as well, check off the second box and choose how many announcements you would like to have listed at a time.

To add an announcement to both the journal homepage and the announcement page, go to:

> User Home > Journal Manager > Announcements

And follow the instructions.

Announcements will appear below the longer descriptive text filled out in the previous step, but above the Table of Contents.
