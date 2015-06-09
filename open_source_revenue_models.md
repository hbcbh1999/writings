## Open Source Revenue Models

The following are Open Source revenue models - not necessarily Free Software revenue models. Free Software respects a users four essential freedoms: to run the program, to study and modify it, to copy it, to redistribute it or modified versions of it for any purpose.

#### RedHat - The Support Model

The support model releases its software as libre but sells additional services such as consulting, support, training, and integration services to earn revenue.

RedHat uses what I will call the "support model". The company gives away open source software but earns revenue by charging a support fee. They sell subscriptions not only to support but also training and integration services.

Fundamentally, this model mandates that customers need 24/7 support, seminars to master the software they are using, and integration help to adapt the software to their business needs. 

If the Software does its job very well, is easy to use and setup, is extremely stable, needs little to no detailed explanation beyond its documentation, and has few dependencies - goals of virtually every software engineer.

**features**

1. Requires: support infrastructure and personnel.
2. Requires: seminars and training materials.
3. Advantage: you over competitors who would offer support services - you are always the leading expert.
4. Advantage: little need for lawyers

* [Why There Will Never Be Another RedHat: The Economics Of Open Source](http://techcrunch.com/2014/02/13/please-dont-tell-me-you-want-to-be-the-next-red-hat/)
* [Red Hat](http://en.wikipedia.org/wiki/Red_Hat)
* [Red Hat 2015 Revenue Report](https://www.redhat.com/de/about/press-releases/red-hat-reports-fourth-quarter-and-fiscal-year-2014-results)

#### MariaDB - The Hacking Model

The hacking model offers the software as free, but charges for additional coding services to end users of the software.

MariaDB uses a derivation of the support model. They offer the same patches, fixes, updates, technical support, etc. that RedHat does, but their focus is on something else. They provide modified binaries and additional tools and coding services to companies that need to adapt MariaDB to their specific needs.

What is interesting about this model is that the software can be extremely stable, powerful, simplistic, and well documented, but the company could still earn revenues if their is enough demand for modifying the software.

An example of this model in practice, could be something like an open source chart visualization library, anyone could use it to create graphs and charts, but the company would earn revenue by selling modified versions that integrate with backend services or provide additional charting functionality.

**features**

1. Requires: you work as a contractor.
2. Requires: a pool of clients needing enough code adaptations/integrations on your software to sustain your business.
3. Advantage: no need to worry about 24/7 support, consulting, etc.
4. Advantage: little need for lawyers

* [The Hacking Business Model](http://www.forbes.com/sites/reuvencohen/2012/07/25/the-hacking-business-model/) 
* [MariaDB Enterpriise](https://mariadb.com/products/mariadb-enterprise)

#### Isotope - The Dual License Model

The dual license model releases source code under 2 distinct licenses, usually one that prevents commercial usage and one that allows for commercial usage.

Metafizzy, the company behind the isotope library, gives its open source software away using the GPLv3 license. However, in order to use the software in commercial applications users are required to purchase various other licenses.

**features**

1. Requires: difficult management of contributions due to dual-licensing
2. Requires: lawyers for prosecuting license infringements

* [Isotope License](http://isotope.metafizzy.co/license.html#isotope-commercial-license-agreement)

#### Mozilla - The Branded Merchandise Model

The Branded Merchandise model sells products that have the branding, slogans, etc. of the software project.

Mozilla sells merchandise with its branding and Firefox logo.

This model lends itself to software projects that have good branding and an image people are proud to wear around.

**features**

1. Requires: good branding and image
2. Requires: maintenance of online store, shipping, and production of real-world goods.

* [Mozilla Gear](https://gear.mozilla.org/)

#### Moodle - The Trademark Model

The Trademark model sells usage of Trademark, logo, and branding.

Moodle sells trademark and logo usage to its commercial partners.

This essentially outsources the hacking model allowing other commercial companies to say they specialize in your software.

**features**

1. Requires: acquiring a trademark 
2. Requires: lawyers for enforcing your trademark
3. Requires: companies will have a reason to use your trademark

* [Moodle Trademark](https://moodle.com/trademarks/)

#### Sharelatex - The SAAS Model

The SAAS model provides open source versions of all its code but charges for online services provided by an online installation of the software.

Sharelatex open sources its code but uses a subscription model for usage of its online service.

In this model companies can easily weigh the positives/negatives of installing your software on their servers and setting up storage and other services themselves or just paying to use the service and not have to worry about all that overhead. It probably works well for projects that have many other dependencies that are not free or difficult to manage, for example storage space, reliability/uptime, advanced search functionality, high performance, security, etc.

**features**

1. Requires: software be applicable as an online service
2. Requires: non-trivial software infrastructure
3. Requires: significant server infrastructure and dedicated uptime.
4. Advantage: easy to reap benefits of open source yet still gives users a reason to purchase.

* [HN Thread](https://news.ycombinator.com/item?id=8965701)

#### Ghost - The Crowdfunding Model

The crowdfunding model sells the product before it is built through marketing and then maintains funding by providing a means for users to pay in order to make feature requests, get special offers, or jointly decide on which bugs to fix.

Ghost raised 200,000 pounds after running a kickstarter campaign to start the development of the software.

This approach focuses almost purely on the end-users. It gives even non-technical users a voice and way to direct product development over time. It has been proven as a good means of bootstrapping the initial funding process, but I can find no examples of projects that have sustainable revenues over time using this approach.

**features**

1. Requires: many users desire to use your product
2. Requires: creating an initial hype
3. Requires: sustaining a long-running user driven community
4. Advantage: easy to get initial funding in order to begin development

* [Ghost Launch after Fundraising](http://www.crowdfundinsider.com/2013/10/24545-bitnami-ghost-blogging-platform-announces-launch-after-raising-funds-on-kickstarter/)

#### Android Games - The Advertising Model

This approach has places in the code where ads are inserted, the creator then earns revenue through the ads.

This approach works well when somehow the software itself allows ads to be inserted without the end-user being conscious of the fact. For instance, a product comparison application that lets advertisers pay to release their items to the initial page in the app under a what's new heading.

**features**

1. Requires: your software include ads
2. Requires: many many end-users to generate significant revenue
3. Requires: making your software user-friendly while still having ad-placement


#### Id Software - The Delayed Model

The delayed model provides the latest version of the software only to paying customers. After a fixed time period modifications by forks are merged back upstream and a new version released, the old version is then released under and open source license and new version only to paying customers.

Id Software has used this approach by releasing its games open source after their life-cycle has ended.

**features**

1. Requires: careful management of release versions
2. Requires: software become better enough to warrent purchase with each release

* [Id Software releases Doom 3 Source Code](http://web.archive.org/web/20131208041324/http://www.h-online.com/open/news/item/id-Software-releases-Doom-3-source-code-1383572.html)


*if you have any thoughts or adjustments you would like to make just send me a PR*
