
![The Gateway Logo](gateway-logo.png "The Gateway Logo")
# Gateway - SEO Tools Technical Standards & Functional Specifications Draft

## Abstract
-----------
This specification is intended for product managers, developers, and executives who are involved in the creation, maintenance, and enhancement of software used for search engine optimization (SEO) analysis, monitoring, and strategy. It serves as a comprehensive guide for those responsible for developing tools that assist in the collection, processing, and interpretation of SEO data. This includes, but is not limited to, software that performs tasks such as crawling websites, analyzing on-page and off-page factors, tracking keyword rankings, monitoring backlinks, and evaluating website performance in search engine results.

Furthermore, this specification is valuable for stakeholders who are interested in ensuring that the software adheres to best practices and industry standards, thereby improving the accuracy, reliability, interoperability, compatibability, and usability of  SEO tools. It aims to provide clear and detailed guidelines that facilitate the correct implementation of features, functionality, and data reporting mechanisms.

This document is also intended for parties focused on enhancing the quality and correctness of the documentation associated with such tools, as well as those responsible for ensuring compliance with these requirements during the development lifecycle. Whether you're building new SEO software from scratch or updating an existing product, adhering to this specification will help ensure that your tool meets the expectations of users and stakeholders by delivering accurate, actionable insights in a standardized manner.

In summary, this specification is a vital resource for anyone involved in the SEO software development ecosystem, from initial conceptualization and design to deployment and ongoing maintenance, aiming to elevate the overall quality and effectiveness of SEO tools within the industry.

## Objective
------------

The goal of this document is to standardize the technical capabilities of SEO software tools pursuant to the issues identified in the December 2016 article on Search Engine Land ["How and Why the SEO Tools Industry Should Develop Technical Standards"](https://searchengineland.com/seo-tools-industry-develop-technical-standards-264983). These standards will enhance data portability, consistency, and accuracy across SEO tools, reducing discrepancies in how data is stored, analyzed, and exported. By establishing a unified framework, it aims to improve interoperability and reliability, ultimately benefiting both users and developers in the SEO industry.

## Scope
--------
Currently, the scope of this specification is limited to providing schemas and functional requirements for all software that is used for monitoring, analyzing and/or improving Organic Search performance both native and software as a service (SaaS) applications.

## Participate
--------------
We encourage all people actively involved in search engine optimization to contribute to this specification. You can [https://github.com/ipullrank/gateway/issues/new](file an issue) or [https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request](submit a pull request). Open issues can be found [here](https://github.com/ipullrank/gateway/issues)

## Compliance
-------------

To comply with this document, search engine optimization solutions must implement all applicable features outlined within. The method for assessing compliance will be established at a later date. Those who are found to be in compliance may use the Gateway logo and will be added to list of certified tools.

## Standard and Process
-----------------------
This section outlines the established guidelines and methodologies that must be adhered to in the development and maintenance of SEO software tools. It provides a structured approach for implementing features and functionaliti, ensuring consistency, accuracy, and quality across different tools and platforms.

### Data Portability

 Data portability is a critical component of modern SEO software, enabling users to seamlessly transfer data between different tools and platforms without loss of information or integrity. This section defines the requirements and protocols for ensuring that data can be exported, imported, and utilized across various systems in a standardized format. It covers the necessary schemas, data types, and formats that must be supported, as well as the mechanisms for handling data transformations and mappings. By adhering to these guidelines, SEO software developers can ensure that their tools provide users with the flexibility to integrate and analyze data from diverse sources, facilitating better decision-making and collaboration. This standard also aims to promote transparency and user control over data, aligning with broader industry trends and regulatory requirements around data ownership and accessibility.

#### Crawl Data File (.CDF)

When exporting data from a crawl, the minimum specification of data points and their order within the exported file is follows.

Where a data point is indicated as 1-n, this means that if there are multiple instances of the feature or data point, they should be included as subsequent columns in the exported file.

- PageID (Internal unique identifier from source tool) 
- URL: The full URL of the crawled page.
- Content Type: The MIME type of the page content (e.g., text/html).
- Status Code: The HTTP status code returned by the page.
- Status: The crawl status (e.g., OK, Blocked, etc.).
- Indexability: Whether the page is indexable (Yes/No).
- Indexability Status: The reason for indexability or non-indexability.
- Title 1-n: The primary title tag of the page.
- Title 1-n Length: The character length of the primary title tag.
- Title 1-n Pixel Width: The pixel width of the primary title tag.
- Meta Description 1-n: The primary meta description of the page.
- Meta Description 1-n Length: The character length of the primary meta description.
- Meta Description 1-n Pixel Width: The pixel width of the primary meta description.
- Meta Keywords 1-n: The primary meta keywords tag of the page.
- Meta Keywords 1-n Length: The character length of the primary meta keywords tag.
- Hn-1-n: The primary H1 heading of the page.
- Hn-1-n Length: The character length of the primary H1 heading.
- Meta Robots 1-n: The primary meta robots tag value.
- X-Robots-Tag 1-n: The primary X-Robots-Tag value in HTTP headers.
- Meta Refresh 1-n: Any meta refresh values found on the page.
- Canonical Link Element 1-n: The canonical link element URL, if present.
- rel="next" 1-n: The next pagination link URL, if present.
- rel="prev" 1-n: The previous pagination link URL, if present.
- HTTP rel="next" 1-n: The next pagination link URL from HTTP headers.
- HTTP rel="prev" 1-n: The previous pagination link URL from HTTP headers.
- amphtml Link Element 1-n: The AMP HTML link element URL, if present.
- Response Time: The server response time in milliseconds.
- Size (bytes): The size of the page content in bytes.
- Transferred (bytes): The number of bytes transferred for the page.
- Total Transferred (bytes): The total bytes transferred for the page including all resources.
- Word Count: The number of words on the page.
- Sentence Count: The number of sentences on the page.
- Average Words Per Sentence: The average number of words per sentence.
- Flesch Reading Ease Score: The readability score based on the Flesch Reading Ease formula.
- Readability: The general readability level of the content.
- Text Ratio: The ratio of text content to the total content.
- Crawl Depth: The depth of the page in the site structure based on the crawl.
- Folder Depth: The folder depth of the URL.
- Link Score: The internal link score based on the number of inlinks and outlinks.
- Inlinks: The total number of internal links pointing to the page.
- Unique Inlinks: The number of unique internal links pointing to the page.
- Unique JS Inlinks: The number of unique JavaScript-rendered internal links pointing to the page.
- % of Total: The percentage of total inlinks relative to all inlinks on the site.
- Outlinks: The total number of outbound links from the page.
- Unique Outlinks: The number of unique outbound links from the page.
- Unique JS Outlinks: The number of unique JavaScript-rendered outbound links from the page.
- External Outlinks: The total number of external links from the page.
- Unique External Outlinks: The number of unique external links from the page.
- Unique External JS Outlinks: The number of unique JavaScript-rendered external links from the page.
- Closest Similarity Match: The URL of the closest similar page based on content.
- No. Near Duplicates: The number of near-duplicate pages found.
- Spelling Errors: The number of spelling errors detected on the page.
- Grammar Errors: The number of grammar errors detected on the page.
- Hash: A unique identifier (hash) for the page's content.
- Response Time: The server response time in milliseconds.
- Last Modified: The last modified date of the page.
- Redirect URL: The URL to which the page redirects, if applicable.
- Redirect Type: The type of redirect (e.g., 301, 302).
- Cookies: The cookies set by the page.
- Language: The primary language of the page content.
- HTTP Version: The HTTP version used (e.g., HTTP/1.1, HTTP/2).
- Mobile Alternate Link: The mobile alternate link element URL, if present.
- URL Encoded Address: The URL-encoded version of the page address.
- Crawl Timestamp: The timestamp of when the page was crawled.
- Embeddings: The embeddings of the page.

These files are specific comma separated value text files, but saved with an extension of .CDF and should be exported with a file name of [Data provider]-[Domain Name]-crawl-[date].cdf. An example filename might be "ScreamingFrog-Example_com-crawl-12072024.cdf." Alternatively, 

Alternatively, this can be delivered as a SQLite database, with a metadata table of metadata of the crawl where relevant metadata is defined as:

- Website: URL of the website
- Crawl Config: The configuration of the crawl
- Rendering Config: The rendering configuration of the crawl
- Version: The version number of dataset (e.g., v1.0, v1.1).
- Author(s): The name(s) of the individual(s) or organization(s) responsible for creating the crawl.
- Creation Date: The date when the crawl was initially created.
- Last Modified Date: The date when the crawl was last modified.
- Crawl Description: A brief description of the crawl’s purpose, contents, and how to use it.
- Data Source: Information about the tool used to generate the crawl 
- Data Collection Method: Description of how the data was collected (e.g., automated crawl, survey, manual entry).
- Data Refresh Frequency: How often the data in the crawl is updated (e.g., daily, weekly, monthly).
- Additional Field Descriptions: Definitions and explanations for each column that is beyond that of the minimum specification.
- Unit of Measurement: The unit of measurement for each relevant field (e.g., USD for prices, % for percentages, ms for response time).
- Data Quality Statement: A statement regarding the accuracy, completeness, and reliability of the data.
- Data Limitations: Any known limitations or caveats regarding the data (e.g., incomplete data for certain dates or regions).
- Access and Permissions: Information about who has access to the crawl and any permissions or restrictions (e.g., view-only, edit rights).
- Tags/Keywords: Relevant tags or keywords that describe the content, to aid in search and categorization.
- Dependencies: Information on any external dependencies the crawl relies on (e.g., linked crawls, external data sources).

#### Link Data File (.LDF)
When exporting data link data for website or webpage the minimum specification of data points and their order within the exported file is follows. 

*Note:* Many of these data points are not available in all link indices. This specification is intended to encourage providers of link data to expand their data points to a level that makes the data more useful for analysis.

- Source URL: The URL of the page from which the link originates.
- Source Title: The title tag of the source page.
- Source Meta Description: The meta description of the source page.
- Target URL: The URL of the page to which the link points.
- Target Title: The title tag of the target page.
- Target Meta Description: The meta description of the target page.
- Open PageRank: The Open PageRank of the target page.
- Open DomainRank: The Open DomainRank of the target page.
- Source Open PageRank: The Open PageRank of the target page.
- Source OpenDomainRank: The Open DomainRank of the target page.
- Source SourceType: Predicted Position in the index based on leaked Google documentation.
- Target SourceType: Predicted Position in the index based on leaked Google documentation.
- Source Domain Spam Score: The spam score of the source domain.
- Source Page Spam Score: The spam score of the source page.
- Link Type: The type of link (e.g., internal, external).
- Link Relationship: The relationship attribute of the link (e.g., "nofollow", "sponsored", "ugc").
- Link Anchor Text: The text of the link that is clickable.
- Link Anchor Text Length: The character length of the anchor text.
- Link Path: The path in the DOM hierarchy where the link is located (e.g., body > div > nav > a).
- Link Target Attribute: The target attribute of the link (e.g., _blank for opening in a new tab).
- Link Position on Source: The position of the link within the source page (e.g., header, footer, main content).
- Is JavaScript Link: Whether the link is generated by JavaScript (Yes/No).
- Is Redirected: Whether the link is redirected to another URL (Yes/No).
- Redirect Target URL: The final URL after redirection, if applicable.
- Redirect Type: The type of redirect (e.g., 301, 302).
- HTTP Status of Target URL: The HTTP status code returned by the target URL.
- Target Indexability: Whether the target page is indexable (Yes/No).
- Target Crawl Depth: The crawl depth of the target URL.
- Link Follow Status: Whether the link is followed by search engine crawlers (e.g., follow, nofollow).
- Link Context: The context in which the link appears (e.g., navigation menu, article body, sidebar).
- Link Distance from Root: The number of links from the homepage to the target URL.
- Target Inlinks: The total number of internal links pointing to the target URL.
- Target Unique Inlinks: The number of unique internal links pointing to the target URL.
- Target External Inlinks: The number of external links pointing to the target URL.
- Link Creation Date: The date when the link was first detected.
- Link Last Seen Date: The last date when the link was detected.
- Linking IP Address: The IP address of the server hosting the source URL.
- Linking Domain Age: The age of the domain hosting the source URL.
- Linking Domain Authority: The domain authority score of the source domain.
- Source Site Category: The category or industry of the source site (e.g., news, ecommerce, blog).
- Source Language: The primary language of the source page content.
- Target Language: The primary language of the target page content.
- Link Sentiment: The sentiment of the content surrounding the link (e.g., positive, negative, neutral).
- Target Content Category: The category of the content on the target page (e.g., blog post, product page).
- Link Traffic Potential: The estimated traffic potential from the source URL to the target URL.
- Source URL Engagement Metrics: Metrics like bounce rate, time on page, and pages per session for the source URL.
- Target URL Engagement Metrics: Metrics like bounce rate, time on page, and pages per session for the target URL.
- Link Click Data: Data on whether the link has been clicked by users, if available.
- Link Bounce Rate: The bounce rate of the source URL.
- Link Time on Page: The time on page of the source URL.
- Link Pages per Session: The pages per session of the source URL.

These files are specific comma separated value text files, but saved with an extension of .LDF.

### Link Metrics

All link indices provide disparate measures of the perceived authority of domains and pages. Ahrefs provides URL Rating, Domain Rating. Majestic provides X, y, Z. Moz provides Page Authority, Domain Authority, MozRank, MozTrust.

While none of these metrics matches up exactly with the measures that Google is using internally, they are reasonable estimations. Unfortunately, since these tools crawl a different pocket of the web, it is difficult to combine the data. Therefore, what is required is a method to tie the datsets together and calculate the best review of a given link profile.

Link Indices require the following methods to ensure users have the ability to do so:

#### Translation of Link Metrics

Organizations providing link indices are required to process the [Common Crawl](http://www.commoncrawl.org) data monthly and publish these numbers as a means for users to calculate the translation of between metrics of across datasets.

#### Public Link Metrics
Alternatively, all link indices are required to process and provide the following public link metrics:

- Open PageRank: The Open PageRank of the target page.
- Open DomainRank: The Open DomainRank of the target page.
- Source Open PageRank: The Open PageRank of the target page.
- Source OpenDomainRank: The Open DomainRank of the target page.
- Source SourceType: Predicted Position in the index.
- Target SourceType: Predicted Position in the index.
- Source Domain Spam Score: The spam score of the source domain.
- Source Page Spam Score: The spam score of the source page.

### TODO

- Crawl Configuration Standardization 
- API Output Standardization
- Rankings Output Standardization

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
 This document was last reviewed on September 26th, 2024.
