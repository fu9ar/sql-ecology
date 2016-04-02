---
layout: lesson
root: .
lastupdated: Mar 4, 2016
contributors: ["Ethan White","Greg Wilson","Josh Herr","Sophie Clayton","Tracy Teal", "Aleksandra Pawlik", "Kevin Vilbig"]
maintainers: []
domain: Public Health
topic: SQL
software: SQL
dataurl: http://omega.uta.edu/~kpv8956/
status: Teaching
---

<!-- USING THIS LESSON TEMPLATE -->
<!-- Lesson specific information is taken from the YAML header at the top of the page -->

<!-- THE LESSON INFORMATION -->

<!-- Get the information from _data/info.yml -->

# Data Carpentry {{ page.topic }} for {{ page.domain }}

Data Carpentry's aim is to teach researchers basic concepts, skills,
and tools for working with data so that they can get more done in less
time, and with less pain. The lessons below were designed for those interested 
in working with {{page.domain %}} data in {{page.topic %}}. 


**Content Contributors: {{page.contributors | join: ', ' %}}**


**Lesson Maintainers: {{page.maintainers | join: ', ' %}}**


###Instructor's setup notes

By default SQLite Manager opens in a separate window and it is not possible to zoom in to enlarge the font
so that it is more readable, especially for students in the back rows.

The way to fix this is to:

1. Open the SQLite Manager
2. Click on the ![Options](img/options_button.png)*Options* button .
3. Chose *Start SQLite Manager: in a new tab*.

You can then use **Ctrl - +** to zoom just like any other web page.



<br> 


#### Lesson status: {{ page.status }} 
<!--
  [Information on Lesson Status Categories]()
-->

<!-- ###### INDEX OF LESSONS ON THIS TOPIC ###### -->

## Lessons:


{% for lesson in site.data.lessons %}

1. [{{ lesson.name }}]({{ lesson.url }})

{% endfor %}



## Data

Data files for the workshop are available here:

[DEMOGRAPHICS](https://raw.githubusercontent.com/fu9ar/sql-pub_health/gh-pages/data/DEMOGRAPHICS.csv)

[MEASURESOFBIRTHANDDEATH](https://raw.githubusercontent.com/fu9ar/sql-pub_health/gh-pages/data/MEASURESOFBIRTHANDDEATH.csv)

[VULNERABLEPOPSANDENVHEALTH](https://raw.githubusercontent.com/fu9ar/sql-pub_health/gh-pages/data/VUNERABLEPOPSANDENVHEALTH.csv)

<br>

<h2>Requirements</h2>

<p>
Data Carpentry's teaching is hands-on, so participants are encouraged to use
their own computers to insure the proper setup of tools for an efficient workflow.
<em>These lessons assume no prior knowledge of the skills or tools</em>, but working 
through this lesson requires working copies of the software described below.
To most effectively use these materials, please make sure to install everything 
<em>before</em> working through this lesson.
</p>



{% if page.software == "Python" %}
{% include pythonSetup.html %}
{% elsif page.software == "Spreadsheets" %}
{% include spreadsheetSetup.html %}
{% elsif page.software == "R" %}
{% include rSetup.html %}
{% elsif page.software == "SQL" %}
{% include sqlSetup.html %}
{% else %}
{% include anySetup.html %}
{% endif %}

<p><strong>Twitter</strong>: @datacarpentry





