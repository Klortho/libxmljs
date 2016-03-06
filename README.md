# @klortho/libxmljs

[![Build Status](https://secure.travis-ci.org/polotek/libxmljs.svg?branch=master)](http://travis-ci.org/polotek/libxmljs)

# Fork of polotek/libxmljs

Package @klortho/libxmljs, version 0.17.2.

This is a fork of [polotek/libxmljs](https://github.com/polotek/libxmljs).
I opened [this pull request](https://github.com/polotek/libxmljs/pull/388), 
but I haven't gotten any response. This fork adds the ability to set the
base-url for XML files, so that references to DTDs, for example, will work.

That pull request is from the *master* branch, here. So, I set the default
branch to cfm-baseurl-for-xml, and published my new version from here.

See also the cfm-libxmljs-mt branch, which was where I started -- forked from
[libxmljs-mt](https://github.com/gagern/libxmljs). I had originally 
submitted [this PR on that repo](https://github.com/gagern/libxmljs/pull/7), but
the author there suggested that I submit my PR upstream, so that's
what I did.

I gave it version 0.17.2, which is one patch up from libxmljs-mt.

----

LibXML bindings for [node.js](http://nodejs.org/)

Install with:

```shell
npm install libxmljs
```

```javascript
var libxmljs = require("libxmljs");
var xml =  '<?xml version="1.0" encoding="UTF-8"?>' +
           '<root>' +
               '<child foo="bar">' +
                   '<grandchild baz="fizbuzz">grandchild content</grandchild>' +
               '</child>' +
               '<sibling>with content!</sibling>' +
           '</root>';

var xmlDoc = libxmljs.parseXml(xml);

// xpath queries
var gchild = xmlDoc.get('//grandchild');

console.log(gchild.text());  // prints "grandchild content"

var children = xmlDoc.root().childNodes();
var child = children[0];

console.log(child.attr('foo').value()); // prints "bar"
```

## Support

* Docs - [http://github.com/polotek/libxmljs/wiki](http://github.com/polotek/libxmljs/wiki)
* Mailing list - [http://groups.google.com/group/libxmljs](http://groups.google.com/group/libxmljs)

## API and Examples

Check out the wiki [http://github.com/polotek/libxmljs/wiki](http://github.com/polotek/libxmljs/wiki).

See the [examples](https://github.com/polotek/libxmljs/tree/master/examples) folder.


## Contributing

To do development, so these once:

```
npm install -g node-gyp
npm install
npm test
npm link
```

From then on, if you make changes:

```
make         #=> incremental build
npm build .  #=> complete rebuild
npm test
```

Start by checking out the [open 
issues](https://github.com/polotek/libxmljs/issues?labels=&page=1&state=open). 
Specifically the [desired 
feature](https://github.com/polotek/libxmljs/issues?labels=desired+feature&page=1&state=open) ones.

### Requirements

Make sure you have met the requirements for 
[node-gyp](https://github.com/TooTallNate/node-gyp#installation). You DO NOT 
need to manually install node-gyp; it comes bundled with node.

