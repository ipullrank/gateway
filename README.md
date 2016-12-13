# Gateway - SEO Tools Technical Standards & Functional Specifications Draft

## Abstract
-----------
This specification is intended for product managers, developers and executives involved in the creation and maintenance of software used in search engine optimization analysis, monitoring and strategy as well as parties interested in improving the correctness of documentation or implementation of regarding the requirements herein.

## Objective
------------

The goal of this document is to standardize the technical capabilities of SEO software tools pursuant to the issues identified in the December 2016 article on Search Engine Land ["How and Why the SEO Tools Industry Should Develop Technical Standards"](http://searchengineland.com/?p=264983). These standards will improve the ability of search engine optimization practitioners to be effective and accurate in the assessments and strategic planning.

## Scope
--------
The scope of this specification is limited to providing schemas and functional requirements for all software that is used for monitoring, analyzing and/or improving Organic Search performance both native and software as a service (SaaS) applications.

## Participate
--------------
We encourage all people actively involved in search engine optimization to contribute to this specification. You can [https://github.com/ipullrank/gateway/issues/new](file an issue) or [https://guides.github.com/activities/forking/](fork the repository and submit a pull request). Open issues can be found [here](https://github.com/ipullrank/gateway/issues)

## Compliance
-------------
To be in compliance with this document, search engine optimization solutions must implement the features of all the relevant features herein. A body for the measurement of compliance will be determined at a later date.

## Standard and Process
-----------------------

### Data Portability

#### Crawl Data File (.CDF)

When exporting data from a crawl, the minimum specification of data points and their order within the exported file is follows.

- PageID (Internal unique identifier from source tool)
- URL
- Status Code
- Content Type
- Title
- Size (Compressed/Uncompressed)
- Content Size (Uncompressed)
- Response Time (millis)
- Depth
- Common Page Rank
- Crawl Time
- Canonical Url

These files are specific comma separated value text files, but saved with an extension of .CDF and should be exported with a file name of [Data provider]-[Domain Name]-crawl-[date].cdf. An example filename might be "ScreamingFrog-Example_com-crawl-12072016.cdf."

Alternatively, these could be exported as a Excel workbook (.xlsx) with the first page being relevant metadata of the crawl where relevant metadata is defined as:

-

#### Link Data File (.LDF)
When exporting data link data for website or webpage the minimum specification of data points and their order within the exported file is follows.

- Source URL
- Dest URL

These files are specific comma separated value text files, but saved with an extension of .LDF.

### Link Metrics

All link indices provide disparate measures of the perceived authority of domains and pages. Ahrefs provides URL Rating, Domain Rating. Majestic provides X, y, Z. Moz provides Page Authority, Domain Authority, MozRank, MozTrust.

While none of these metrics matches up exactly with the measures that Google is using internally, they are reasonable estimations. Unfortunately, since these tools crawl a different pocket of the web, it is difficult to combine the data. Therefore, what is required is a method to tie the datsets together and calculate the best review of a given link profile.

Link Indices require the following methods to ensure users have the ability to do so:

#### Translation of Link Metrics

Organizations providing link indices are required to process the [Common Crawl](http://www.commoncrawl.org) data from [DATE] and publish these numbers as a means for users to calculate the translation of between metrics of across datasets.

#### Public Link Metrics
Alternatively, all link indices are required to process and provide the following public link metrics:

- Public Page Rank
- Public Domain Rank
- Public

### Crawl Capabilities

- Headless Crawling
--* Headless Chrome
--* PhantomJS

- User Agent Switching

- Throttling


### Rankings

- Granular Geolocation
-

### The Open Rankings Initiative


#### Document Owner
-------------------
Until another person or group of people has been identified, the owner of this document is Michael King (mike@ipullrank.com).


#### Document Approver
----------------------
 Until another person has been identified, the owner of this document is Michael King (mike@ipullrank.com).

#### Effective Date
-------------------
 This document is a draft, and therefore will not be enforced until its specifications are completed and are collectively agreed upon.

#### Last Reviewed Date
-----------------------
 This document was published and last reviewed on December 7th, 2016
