# PayPal Plugin Configuration for OJS

 Occasionally, a journal will require a payment module in OJS. Very occasionally. OJS only really supports [PayPal](http://www.paypal.com) as an official payment plugin. However, it's connectivity is a little dated. You might experience some frustration in connecting the two when the OJS pages are asking you for information from PayPal that you might think doesn't exist or is deeply buried in their settings. In February of 2014, I took a look at configuring the PayPal plugin. These are, roughly, the steps we took at that time. 

## Step 1: OJS

1. Go to **Journal Manager**.
2. **Payment**.
3. Click on **Fee Payment Methods** from the sub-menu.
4. Enable PayPal. 
5. For the IPN URL, you'll notice that right below the field it gives you two URLs. Use the one it says for live sites (this one: https://www.paypal.com/cgi-bin/webscr).  
6. Put your PayPal username in the field below.

## Step 2: PayPal

1. Login to Paypal. 
2. Click on the link that says "Profile". 
3. On the left sidebar, click "My Selling Tools".
4. Under the header "Getting Paid and Managing My Risk" you'll see a line that says **Instant payment notifications**.
5. On the right, on that line, click Update. 
6. Enable IPN. 
7. Paste in the same URL you used in OJS. 

## Step 3: **OJS**

1. Go back to **Options** in the sub-menu and populate prices for everything there you wish to have a price for. 
2. Test at home, ideally, so you're not part of an institutional subscription. 

That ought to get you most of the way there. 

It's worth noting that the IPN (Instant Payment Notification) is something that is filed under "Classic APIs" in [PayPal's developer documentation](https://developer.paypal.com/webapps/developer/docs/classic/products/instant-payment-notification/). This suggests that the plugin is outdated in some respect. There may be modifications to the plugin planned by PKP in the near future.  

