# fermata-chargify

This is a Chargify API plugin for [Fermata](https://github.com/natevw/fermata). It takes care of just a few boring bits, leaving you with raw unfettered Fermata-style direct usage of the bona fide Chargify API.


## Setup

This is a standard [Fermata plugin](https://github.com/natevw/fermata#plugins), so please see that documentation or take a look at the the [Fermata CouchDB plugin docs](https://github.com/natevw/fermata-couchdb#setup) for example setup.


## Example usage

Here's what using this plugin can look like:

    var site = fermata.chargify("my-site", "secret key");
    
    site.subscriptions.get(function(e, d) {
      if (e) console.error(e,d);
      else console.log(d);
    });
    
    var some_sub = wrapped_site.subscriptions[42];
    some_sub.get(function(e, d) {
      if (!e) console.log(d.subscription.state);
    });
    
    
## Plugin API

The following documentation assumes this plugin has been registered into `'fermata'` with the name `'twitter'`:

- `fermata.chargify(site_name, api_key)` — Returns a "URL proxy" object for Chargify's API (at "https://your-site-name.chargify.com") with authorization credentials configured.

Behind the scenes, this plugin **adds the ".json" extension to URLs for you**. But beyond that, it's simply [standard Fermata usage](https://github.com/natevw/fermata#complete-documentation) as you talk to [Chargify's standard API](http://docs.chargify.com/api-resources) — by design!


## License (MIT)

Copyright © 2011–2015 Nathan Vander Wilt.

Released under the terms of the MIT License:

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
