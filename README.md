# Introduction
This is a small client used to order sip club drinks from panera
it is not 'full featured' as you can't do things such as order 
specific variants for tea, or add pumps of syrup to drinks, but 
it can order a pepsi, a coffee, or other simple drinks.

## Logging In
Before one can use `sippy`, they will need to provide the 
credentials for their account. To do this, go to the panera website
[here](https://www.panera.ca/en-us/home.html). Next, open the developer
tools with f12 and click on the Network tab of the newly openned window.
Then, log into panera using the Sign in button on the page. once you
are logged in.

Search for 'auth' in the Filter URLs bar of the developer tools panel.
right click the latest request that is left and click Copy value followed
by Copy Response.

Finally, run `sippy login '<VALUE_COPIED>'` ( remember the single 
quotes around the value). It should look something like:
```bash
sippy login '{"accessToken":"aaaaaaaa-aaaa-aaaa-aaaa-aaaaaaaaaaaa", ...'
```

Once this is run, the credentials will be stored in your config directory
as `sippy.json`

## Usage
After logging in, you can order!
Find the panera location that you'd like to order from,
You can check [here](https://delivery.panera.ca/cafeLocations/), 
search for the panera location you would like and then look for 
the number after the hashtag (this is the location's ID).
For fellow RPI'ers, the Union's Panera location ID is 203162.

Next, grab the menu with `sippy menu <LOCATION-ID>`. Find the row
with the item you want, and then note the item's ID in the first
column. 

Finally, order the item with `sippy order <LOCATION-ID> <ITEM-ID>`