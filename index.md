---
layout: posts
permalink: /
---

  <style>
      body {margin: 0;font-family:'Roboto Condensed';}
      
      header {background-image: linear-gradient(to right, rgba(67,171,159,0.8), rgba(36,83,97,1)); padding: 30px; text-align: center; font-size: 25px; color: white;}
      
      h2 {
        color: rgba(67,171,159,1);
      }

      h3 {
        color:  rgba(36,83,97,1)
      }

      #contentPara, #contentList {margin-left: 10%; margin-right:10%;}
      #contentHeader {margin-left: 5%; margin-right:5%;font-size:22px}
      #subHeader {font-style:italic;font-size:15px;}
      #contentSubHeader {margin-left: 15%; margin-right:15%;font-size:18px}
      #contentSubPara {margin-left: 15%; margin-right:15%;}
       
      .content {
        padding: 0 18px;
        background-color: white;
        max-height: 0;
        overflow: hidden;
        transition: max-height 0.2s ease-out;
      }
      
      .collapsible:after {
        content: '\02795'; /* Unicode character for "plus" sign (+) */
        font-size: 13px;
        color: white;
        float: right;
        margin-left: 5px;
      }

      .active:after {
        content: "\2796"; /* Unicode character for "minus" sign (-) */
      }

       .content-table {
        border-collapse: collapse;
        margin: 15px 15px 10px 10px;
        font-size: 0.9em;
        min-width: 400px;
        border-radius: 5px 5px 0 0;
        overflow: hidden;
        box-shadow: 0 0 20px rgba(0, 0, 0, 0.15);
      }


      .content-table thead tr {
        background-color: #245361;
        color: #ffffff;
        text-align: left;
        font-weight: bold;
      }

      .content-table th,
      .content-table td {
        padding: 12px 15px;
      }

      .content-table tbody tr {
        border-bottom: 1px solid #dddddd;
      }

      .content-table tbody tr:nth-of-type(even) {
        background-color: #f3f3f3;
      }

      .content-table tbody tr:last-of-type {
        border-bottom: 2px solid #245361;
      }

      .content-table tbody tr.active-row {
        font-weight: bold;
        color: #245361;
      }
}
  </style>

<header>

  <h1>The IDOR Wall of Shame</h1>
  <p id="subHeader">A list of companies that treat insecure direct object references as intended functionality, not a security requirement</p>
</header>

<summary>
<h2>What is an insecure direct object reference?</h2>
</summary> 
An insecure direct object reference (IDOR) can be classified as an access control vulnerability, which may appear when an application exposes references to resources, allowing these resources to be accessed directly through user-supplied input, without requiring authorization.

<br>

<summary>
<h2>How can a threat actor exploit this vulnerability?</h2>
</summary>
A threat actor may exploit this vulnerability using a variety of techniques:

- Performing a brute force attack against vulnerable application functionality to gain unauthorized access to resources via a direct request to the resource.
- Accessing the server logs of a web application or browsing history of an end user to obtain access to URLs that directly reference and link to sensitive data stored on a web application server.

<br>

<summary>
<h2>Why should I care?</h2>
</summary>
When a company is provided with personal data, they are expected to protect this data and withhold it from unauthorized parties.

The companies listed in this article allow for uploaded user data, in the form of photos and documents, to be accessible to any unauthorized party that can directly reference the data. Thus, they are not taking the necessary steps to protect their user’s personal data.

The listed companies have been contacted and communicated with. Their refusal to the patch the functionality of their applications is what prompted the release of this article.

Should you choose to provide your data to the entities listed below, be warned: Your uploaded data resides on a server, unprotected from any user that directly reference the resource.

<br>

<summary>
<h2>Historical Breaches involving insecure direct object references</h2>
</summary>
IDORs are historically problematic, as they can lead to data leaks and even account takeovers. Due to the prevalence of IDORS within web applications, it has led to some major data breaches over the past few years.

<summary>
<h3>The First American Financial Data Leak</h3>
</summary>
<summary>
In 2019, a security researcher discovered that the First American Financial website had an IDOR vulnerability which left hundreds of millions of sensitive files exposed. These files contained personal identifiable information such as social security numbers, drivers’ licenses, and bank account numbers, which could all be viewed without any authentication. Not only could a valid URL be viewed by anyone, modifying a single digit within this URL would link to a different document.
</summary>

<summary>
<h3>United States Department of Defense website</h3>
</summary>

<summary>
In 2020, a security firm discovered an IDOR vulnerability on the United States Department of Defence website. This instance of IDOR allowed for an unauthenticated account takeover, as the user ID and username parameters could be modified in a request to change the account password of any user.
</summary>

<br>

## The Wall

<table class="content-table">
  <thead>
    <tr>
      <th>Vendor</th>
      <th>Disclosure Date</th>
      <th title="Still Accessible After Deletion">SAAD</th>
      <th title="Still Accessible After Account Deletion">SAAAD</th>
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