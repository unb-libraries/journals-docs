# OJS Journal Styles Guide
Each of our journals in OJS has it's own basic tweaks to our site-wide style sheet for a more tailored display. The modifications are typically simple, and usually only adjust the following few items:

- Link colors
- Sidebar header colors
- Specific details for HTML display including:
    - Sizing and format of headers to match print
    - Any other adjustments as necessary…

Style modifications are done with a single CSS file per journal and all existing styles can be found on our Github repository.

Here's a sample file, from Atlantic Geology:

```
/**
 * AGEO Style Sheet for OJS
 * Written by Michael Nason @ ETC UNB 2011
 */
 
 /**
  * Journal-Style
  */
  
a:link {
	color: #910101;
}

a:active {
	color: #000000;
}

a:visited {
	color: #910101;
}

a:hover {
	color: #000000;
	background-color: inherit;
}
	

/**
 * Sidebar-Style
 */

#sidebar a:link {
	color: #910101;
	text-decoration:none;
}

#sidebar a:active {
	color: #000000;
	text-decoration:none
}

#sidebar a:visited {
	color: #910101;
	text-decoration:none;
}

#sidebar a:hover {
	color: #000000;
	background-color: inherit;
}

/**
 * Article-Display
 */


/**
* Body Headers 2C6988
*/

#document-body div.section2 h1 {
    font-size: 1.2em;
    text-transform:uppercase;
}

#document-body div.section2 h2 {
    font-size: 1.2em;
}

#document-body div.section2 h3 {
    font-size: 1.2em;
    font-style: italic;
}
```

It's pretty clear what's being modified in these cases. And the Body Headers section adjusts h1-h3 to properly match the scale and styling of the journal itself.

If a journal does not have detailed markup, or if the HTML display for that journal is quite basic, no adjustments to article display need to be made.

All custom css files are uploaded within OJS's interface, by going to:

- **USER HOME**
    - Journal Manager
        - Setup
            - Step 5. The Look
                - Scroll down the page to section “5.6 Journal Layout”
                - Upload your css file, and click “Save” at the bottom.
Easy peasy.