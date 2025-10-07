---
layout: post
title: "Reading through Jekyll docs"
date: 2024-01-09 19:12
categories: learning jekyll
permalink: jekyll-basics-learning
description: "Notes from working through Jekyll documentation, covering installation, Liquid templating, front matter, layouts, and basic Jekyll functionality."
---

<h2 id="#table-of-contents">Table of Contents</h2>

<ul>
    <li><a href="#overview">Overview</a>
    <ul>
    </li> 
        <li><a href="#step-by-step-tutorial">Step by step tutorial</a></li> 
    </ul>
    </li>
        <li><a href="#front-matter">Front Matter</a></li>
        <li><a href="#liquid">Liquid</a></li>
        <li><a href="#layouts">Layouts</a></li>
        <li><a href="#Includes">Includes</a></li>
        <li><a href="#data-files">Data Files</a></li>
        <li><a href="#assets">Assets</a></li>
        <li><a href="#blogging">Blogging</a></li>
        <li><a href="#collections">Collections</a></li>
        <li><a href="#deployment">Deployment</a></li>
    </ul>
    </li>
</ul>

<br><br>









<br><hr><br>

<!-- OVERVIEW -->

<h2 id="overview" align="center">OVERVIEW</h2>

<br><hr><br>

<a href="https://jekyllrb.com/docs/">Jekyll Documentation</a>

<br><br>

<p>
    I'm going to go through the Jekyll documentation to familiarise myself with how it works. This 
    will include everything from the installation to blogging etc
</p>

<br><br>

<h3>Compiling the site</h3>

<h4>Setup</h4>

<p>To build the site</p>

<code>
    jekyll build
</code>

<br><br>

<p>To compile the code then host this on localhost:4000</p>

<code>
    jekyll serve
</code>

<br><br>

<p>The livereload flag can be used to ensure that changes are update to the localhost view when 
    saving the document
</p>

<code>
    jekyll serve --livereload
</code>

<br><br>

<p>These two flags can be used to manually set the address / port if there are conflicts locally
</p>


<code>
    --host or --port
</code>

<br><br>










<br><hr><br>

<!-- LIQUID -->

<h2 id="liquid" align="center">LIQUID</h2>

<br><hr><br>

<h3>What is Liquid</h3>
<p>
    Liquid is the thing which drives the templating system used by Jekyll. It does this using 
    three main components
</p>

<br>

<p><b>Components:</b></p>
<ul>
    <li>Objects</li>
    <li>Tags</li>
    <li>Filters</li>
</ul>

<br>

<h3>Objects</h3>

<p><b>Example: </b></p>

<p>
    <code>
        {% raw %}
        {{ page.title }}
        {% endraw %}
    </code>
    
</p>
    
<p>
    The above is a variable, if printed it would display the title defined in the pages header 
    which is written inbetween the liquid tags
</p>

<br>

<h3>Tags</h3>
<h4>Control flow</h4>

<p><b>Example: </b></p>

<p>
    <code>
        {% raw %}
        {% if customer.name == "kevin" %} <br>
        &nbsp;&nbsp;&nbsp;Hey Kevin! <br>
        {% elsif customer.name == "anonymous" %} <br>
        &nbsp;&nbsp;&nbsp;Hey Anonymous! <br>
        {% else %} <br>
        &nbsp;&nbsp;&nbsp;Hi Stranger! <br>
        {% endif %} <br>
        {% endraw %}
    </code>

    
</p>
    
<p>
    The above is an if statement with else if statements. When it runs it will first check if the pages title contained 
    within the liquid tags is "awesome shoes". If it is then it would output these shoes are 
    awesome to
</p>



<br><br><br><br><br>

<br><hr><br>

<!-- FRONT MATTER -->

<h2 id="front-matter" align="center">FRONT MATTER</h2>

<br><hr><br>

<h3>Front matter defaults</h3>
<a href="https://jekyllrb.com/docs/configuration/front-matter-defaults/">Defaults article</a>

<br><br>

<p>
    You can setup front matter defaults within the _config.yml file. To do 
    this you would first define a scope e.g. any file in the _projects folder 
    then you would set certain default variables
</p>

<p>
    You would set a default such as the post "type"
</p>

<br>

<p><b>Things to note:</b></p>
<ul>
    <li>Globbing causes perfomance issues</li>
    <li>Presedence when defining from config is top to bottom, when 
        defining from the post itself any liquid will overwrite the 
        defaults which are showing on config
    </li>
</ul>


<br><hr><br>

<!-- LAYOUTS -->

<h2 id="layouts" align="center">LAYOUTS</h2>

<br><hr><br>







<br><hr><br>

<!-- INCLUDES -->

<h2 id="includes" align="center">INCLUDES</h2>

<br><hr><br>







<br><hr><br>

<!-- DATA FILES -->

<h2 id="data-files" align="center">DATA FILES</h2>

<br><hr><br>





<br><hr><br>

<!-- ASSETS -->

<h2 id="assets" align="center">ASSETS</h2>

<br><hr><br>




<br><hr><br>

<!-- BLOGGING -->

<h2 id="blogging" align="center">BLOGGING</h2>

<br><hr><br>





<br><hr><br>

<!-- COLLECTIONS -->

<h2 id="collections" align="center">COLLECTIONS</h2>

<br><hr><br>





<br><hr><br>

<!-- DEPLOYMENT -->

<h2 id="deployment" align="center">DEPLOYMENT</h2>

<br><hr><br>







<details>
<summary><b>Time Tracking</b></summary>

<br>

<h4><b>Research 2</b></h4>
<p>14/02/24 | start 22:44 | end 00:10 | 1 hour 26 minutes</p>
<ul>
    <li>Formatted headings for each section within the Jekll docs</li>
    <li>Created TOC and linked to said headings</li>
    <li>Complete initial research around Liquid and front matter</li>
    <li>Touched on front matter defaults which can be added to the config.yml file</li>
</ul>

</details>