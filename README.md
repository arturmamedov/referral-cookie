# referral-cookie
Get traffic refferal sources, utm_parmas cookies (for first time visit and the last one)



Create one or two cookies with referral sources of user that visit the website

| Cookie name   | Purpose       |
| :------------ |:--------------|
| `js_referral` | the first visit of user, remain the same at every successive visit |
| `js_referral_returned` | the last user visit, change every time the user visit website |


##### For read cookies you can use:

```js

// this return the cookie as it is (so you must decode it fo read)
var session = crumbleCookie('js_referral'),
    session2 = crumbleCookie('js_referral_returned');

// First time session (only the first time visit)
if (typeof session != 'undefined') {
    // use decodeURIComponent(...) for get the full cookie string 
    document.getElementById('js_referral').innerHTML = decodeURIComponent(session);
    
    // use readLogic('cookie_name') for retrieve object with configured $cookie_params
    console.log(readLogic('js_referral'));
}
// Last time session (ever the last time visit)
if (typeof session2 != 'undefined') {
    // use decodeURIComponent(...) for get the full cookie string
    document.getElementById('js_referral_returned').innerHTML = decodeURIComponent(session2);
    
    // use readLogic('cookie_name') for retrieve object with configured $cookie_params
    console.log(readLogic('js_referral_returned'));
}

```  

###### Formats with cookieToString():

- direct

- google (cpc | gclid)

- google (cpc | CampaignName | term: if, set | content: if set)

- newsletter (email | campaignName | term: uno, due, tre | content: content)

- google (organic | term: (not provided))

- someweb.site (referral)

- arianna.libero.it (organic | term: query of search)

- bing.com (organic | term: query of search)

- also: yahoo, yandex, baidu, ask, virgilio `(organic)` you can configure $search_engines

Example: You can use it in a hidden input in forms for submit info about referrals