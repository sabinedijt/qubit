# Qubit

Reusable solutions to be used in Qubit experiences

- nonBounce tracking
- jqPoller
- jsPoller


## nonBounce tracking
This sets a cookie on a specific page and tracks the cookie on every other page
You can call it by using the following line:
```
var nb = new window.globalQBCode.nonBounce(options).both(pageArray)
```
pagearray is an array with pathnames of the pages you want to track, doesn't have to include pre and post slashes. For a clean path, for example the homepage, use 'hp'
Example: ['hp', 'product']

If your nonBounce tracking requires specific conditions, you can initialize using
```
var nb = new window.globalQBCode.nonBounce(options)
```
And then set and track in the places you want using, for example:
```
nb.setCookie('hp')
```
and
```
nb.trackCookie('hp')
```

When you use the nonBounce you won't have to import another cookieman in your experience, you can use the one from the globalcode by calling
```
window.globalQBCode.cm
```


## jqPoller
This is a poller like qubit's core poller, but instead of using qubit's jQuery, it used the jquery you might already have implemented in your website, to prevent double loading of jQuery. Ask qubit about possibly removing the jQuery from their core for your website.
You can call it in the same way as the qubit poller using
```
window.globalQBCode.jqpoller(elementArray, function(the callback elements you want to use){
//do something with your callback elements if you want
})
```
Example:
```
window.globalQBCode.jqpoller(['body header', 'window.someProperty'], function(header, someprop){
//do something with the header, which returns $('body header') and someprop, which returns the value of window.someProperty
})
```

## jsPoller
This is a poller like Qubit's core poller, but it uses no jQuery whatsoever.
You can call it in the same way as the Qubit poller using
```
window.globalQBCode.jqpoller(elementArray, function(the callback elements you want to use){
//do something with your callback elements if you want
})
```
Example:
```
window.globalQBCode.jqpoller(['body header', 'window.someProperty'], function(header, someprop){
//do something with the header, which returns window.querySelector('body header') or document.querySelectorAll('body header'), depending on the number of elements found, for ease of access
//And someprop, which returns the value of window.someProperty
})
```
