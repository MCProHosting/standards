# External Packages

Preexisting packages can be great resources. There is nothing wrong with depending on an external package, but do follow these guidelines:

 * Do not use packages which are not unit tested. *Why?* a package without tests more prone to breakage, and likely not coded as solidly.
 * It is preferred to use popular and well-maintained packages over packages that have not been updates in months/years, or packages that are brand new or have very few installs. *Why?* Very young packages are often unstable, and very old packages may not conform to recent conventions or language features.
 * Try to use a single large, well-maintained package over many packages which overlap greatly or have extremely small uses. *Why?* To avoid [dependency hell](http://en.wikipedia.org/wiki/Dependency_hell).
