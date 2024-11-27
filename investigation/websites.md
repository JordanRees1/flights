# Comparison sites

## Site Requirements
1. A site needs to have a parsable URL 
1. Quick search time <5-10s max
1. Ideally needs to have no JS authentication
1. Limited captcha or at least HTML that loads in the background
1. Parsable HTML is nicer - want to be careful of generated css div names and classes as these will change frequently. Are we able to create a job that can find these CSS tags programatically?

## Sites Found

Below are some of the most suitable sites I could find that seem the most parsable and have limited bot/JS checks in place currently as of 11/24.

1. kayak: https://www.kayak.co.uk/
Format of URL: flights/MAN-GVA/2024-12-21/?sort=price_a&fs=takeoff=0600,1300;stops=0;legdur=-180;
Options appended to URL: Y 
Data privacy popup: Y

Kayak is probably the largest and therefore most risky? Will they have the best anti bot checks? However 
CSS div class of the price "f8F1-price-text" - 27/11/24


2. Momondo: https://www.momondo.co.uk/
Format of URL: flight-search/MAN-GVA/2024-12-21/2024-12-28?ucs=cix4c6&sort=bestflight_a
Options appended to URL: Y 
Data privacy popup: Y

Another very similar search format to kayak. Therefore would be useful as a backup potentially. Limited amount of options on the first page and requires page clicks to get all the prices (however can sort by price).
CSS div class of the price "f8F1-price-text" - 27/11/24 (This looks like it is built on the same engine as KAYAK)


3. cheapflights: https://www.cheapflights.co.uk/
Format of URL: flight-search/MAN-GVA/2024-12-21/2024-12-28?fs=fdDir=true;stops=~0&ucs=fqgv02&sort=bestflight_a
Options appended to URL: Y 
Data privacy popup: Y

Very quick to search. A really large number of flights shown on page 1, so great to get a true average of the costs.
CSS div class of the price "f8F1-price-text" - 27/11/24 (This looks like it is built on the same engine as KAYAK and Momondo)


4. opodo: https://www.opodo.co.uk/
Format of URL: travel/#results/type=R;from=MAN;to=GVA;dep=2024-12-21;ret=2024-12-28;buyPath=FLIGHTS_HOME_SEARCH_FORM;internalSearch=true
Options appended to URL: N
Data privacy popup: Y

Bit more of a messy URL and the search is quite slow. However there are lots of options when the list is loaded. Options are not appended to to URL.

CSS div class of the price "money-integer css-1p8lfkf e139ay0z2" - 27/11/24. There is a div with the text "Non-discounted Price", then 7 'layers' down there is the money-integer if that is useful 


5. compareflights: https://book.compareflights.co.uk/
Format of URL: flights/MAN2112GVA28121 - {DEP_CODE}{DD-MM}{DEST_CODE}{DD-MM}1???
Options appended to URL: N
Data privacy popup: N

The search has a timer but loads quickly. Negative of this one is that the sorting and options are not appended to the URL...

CSS div class of the price "currency_font currency_font--gbp" - 27/11/24 this span is contained within a more readable (less dynamic) 'strong' with class "ticket-action-button-deeplink-text__price--not-mobile"