---
layout: posts
permalink: /
title: "The IDOR Wall of Shame"
description: "A list of organizations that treat insecure direct object references as intended functionality, not as a security vulnerability."
twitter_social_image: "https://hideourdata.github.io/assets/images/idor_1200x630.png"
og_social_image: "https://hideourdata.github.io/assets/images/idor_1200x628.png"
---

<header>
<h1>The IDOR Wall of Shame</h1>
<p>
A list of organizations that treat insecure direct object references
as intended functionality, not as a security vulnerability.
</p>
</header>
<main>
<section class="background">
<span class="section-label">Background</span>
<div class="content-block">
<h2 id="what-is-an-insecure-direct-object-reference">
What is an insecure direct object reference?
</h2>
<p>
An insecure direct object reference (IDOR) can be classified as an
access control vulnerability, which may appear when an application
exposes references to resources, allowing these resources to be
accessed directly through user-supplied input, without requiring
authorization.
</p>
</div>
<div class="content-block">
<h2 id="what-is-an-insecure-direct-object-reference">
How can a hacker exploit this vulnerability?
</h2>
<p>
A hacker may exploit this vulnerability using a variety of
techniques:
</p>
<ul>
<li>
Performing a brute force attack against vulnerable application
functionality to guess valid references and gain unauthorized
access to resources via a direct request to the resource.
</li>
<li>
Accessing logs from web servers or intermediaries (e.g., web
proxies, gateways, CDNs, etc.), or the browsing history of an
end user, to obtain URLs that directly reference and link to
sensitive data stored by the application.
</li>
</ul>
</div>
<div class="content-block">
<h2>Why should I care?</h2>
<p>
When a company is provided with personal data, they are expected
to protect this data from unauthorized access.
</p>
<p>
The companies listed on this site allow for users to upload files,
in the form of photos and documents, to be accessible by any
unauthorized party that can directly reference the data. They are
not taking the necessary steps to protect their users??? personal
data from unauthorized access.
</p>
<p>
The listed companies have been contacted and communicated with.
They are added to this list if they refuse or fail to address the
vulnerability in their applications in a timely manner.
</p>
<p>
Should you choose to provide your data to the entities listed
below, be warned: Your uploaded data resides on a server,
unprotected from unauthorized access by anyone that can directly
reference the resource.
</p>
</div>
</section>
<section class="history">
<span class="section-label">Historical Incidents</span>
<div class="content-block">
<h2>
Historical breaches involving insecure direct object references
</h2>
<p>
IDORs are historically problematic, as they can lead to data leaks
and even account takeovers. Due to the prevalence of IDORs within
web applications, it has led to some major data breaches over the
past few years.
</p>
</div>
<div class="timeline">
<ul>
<li>
<h3>The First American financial data leak</h3>
<p>
In 2019, a security researcher discovered that the First
American Financial website had an IDOR vulnerability which
left hundreds of millions of sensitive files exposed. These
files contained personal identifiable information such as
social security numbers, drivers??? licenses, and bank account
numbers, which could all be viewed without any authentication.
Not only could a valid URL be viewed by anyone, modifying a
single digit within this URL would link to a different
document.
</p>
</li>
<li>
<h3>Amadeus Travel Software</h3>
<p>
In 2019 the head of a security firm discovered that valid
boarding passes of other travellers could be downloaded from
travel software developed by the Amadeus IT Group, who provide
software used by 500 airlines. This instance of IDOR was
discovered when the researcher noticed the URL structure of
his own boarding pass and realized the ID parameter was
vulnerable. Through this vulnerability a threat actor could
obtain customer PII such as phone numbers and contact
information.
</p>
</li>
<li>
<h3>United States Department of Defense website</h3>
<p>
In 2020, a security firm discovered an IDOR vulnerability on
the United States Department of Defence website. This instance
of IDOR allowed for an unauthenticated account takeover, as
the user ID and username parameters could be modified in a
request to change the account password of any user.
</p>
</li>
<li>
<h3>The IRCTC???s Ticketing Portal</h3>
<p>
In 2021, a 17-year-old student discovered an IDOR
vulnerability in the ticketing portal of the Indian Railway
Catering and Tourism Corporation (IRCTC) when trying to book a
ticket. This vulnerability allowed him to access passenger
data such as names, ages, and journey related data.
</p>
</li>
</ul>
</div>
</section>
<section class="wall">
<span class="section-label">The Wall</span>
<div class="content-block">
<p>
The following are the list of companies we have identified as
treating insecure direct object references as intended
functionality, not as a security vulnerability.
</p>
</div>
<div class="wall-table-container">
<table class="wall-table">
<thead>
<tr>
<th>Vendor</th>
<th>Privacy Policy</th>
<th>Disclosure Date</th>
<th>Still Accessible After Deletion</th>
<th>Still Accessible After Account Deletion</th>
<th>Last Checked</th>
<th>Sample URL</th>
<th>Data Type</th>
</tr>
</thead>
<tbody>
{% assign company = site.companies %}
{% for c in company %}
<tr>
<td markdown="span"><a href="{{ c.company_url }}">{{ c.name }}</a></td>
<td markdown="span">{{ c.privacy_policy }}</td>
<td markdown="span">{{ c.disclosure_date }}</td>
<td markdown="span">{{ c.saad }}</td>
<td markdown="span">{{ c.saaad }}</td>
<td markdown="span">{{ c.last_checked }}</td>
<td markdown="span">{{ c.sample_url }}</td>
<td markdown="span">{{ c.data_type }}</td>
</tr>
{% endfor %}
</tbody>
</table>
</div>
</section>
</main>
