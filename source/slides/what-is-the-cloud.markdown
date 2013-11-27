---
layout: page
title: "what is the cloud"
comments: false
sharing: true
footer: true
---

Slides from the "cloud and NGS data analysis" course that we ran on August 2013.

-----

<div id="slides" >
  <iframe class="dzslides_embedded" allowfullscreen mozallowfullscreen webkitallowfullscreen>
    <!DOCTYPE html>
<head>
<meta charset="utf-8">
  <meta name="author" content="Eduardo Pareja-Tobes" />
  <title>the cloud?</title>
  <style type="text/css">
table.sourceCode, tr.sourceCode, td.lineNumbers, td.sourceCode {
  margin: 0; padding: 0; vertical-align: baseline; border: none; }
table.sourceCode { width: 100%; line-height: 100%; }
td.lineNumbers { text-align: right; padding-right: 4px; padding-left: 4px; color: #aaaaaa; border-right: 1px solid #aaaaaa; }
td.sourceCode { padding-left: 5px; }
code > span.kw { color: #007020; font-weight: bold; }
code > span.dt { color: #902000; }
code > span.dv { color: #40a070; }
code > span.bn { color: #40a070; }
code > span.fl { color: #40a070; }
code > span.ch { color: #4070a0; }
code > span.st { color: #4070a0; }
code > span.co { color: #60a0b0; font-style: italic; }
code > span.ot { color: #007020; }
code > span.al { color: #ff0000; font-weight: bold; }
code > span.fu { color: #06287e; }
code > span.er { color: #ff0000; font-weight: bold; }
  </style>
<link href='http://fonts.googleapis.com/css?family=Bitter:400,700,400italic|Open+Sans:300italic,400italic,600italic,400,300,600' rel='stylesheet' type='text/css'>
<style>
  html { background-color: #425331; }
  body { 
    background-color: #f9fcfe; 
    color: #414141;
    text-align: left;
  }
  /* A section is a slide. It's size is 800x600, and this will never change */
  section {

    display: inline-block;
    font-family: Open Sans, sans;
    font-weight: 400;
    font-size: 225%; /* 16 * 2.25 = 36 */
    color: #535353;
  }

  p { margin-bottom: 1.333em; }
  strong { color: #b8913d; } 
  em {  font-weight: 400; color: #121212; }
  code {  font-family: PT Mono; font-size: 76%; }
  address, blockquote, dl, fieldset, p, form, h1, h2, h3, h4, 
  h5, h6, hr, ol, pre, table, ul, dl { 
    vertical-align: middle;
  }
  h1, h2, h3 {
    margin-top:0; margin-bottom:0;
    letter-spacing: -1px;
    text-align: center;
    font-family: Bitter;
    font-weight: normal;
    color: #b8463d;
  }
  h1 {  font-size:2em; padding: 0.6666em 0; }
  h1 { padding-top: 0; }
  h2 {  font-size:1.75em; padding:0.381em 0;  }
  h3 {  
    font-size: 1.5em; 
    padding-top: 0;
    padding-bottom: 0.8888em;
    padding-left: 0;
    padding-right: 0;
    text-align: left; 
  }
  section.titleslide h1 {}
  h1.title { 
    text-align: right;
    font-size: 2.4em;
    font-family: Bitter;
    font-weight: bold; 
    font-style: italic;
    color: #b8913d;
    padding: 0.6666em 0;
    padding-bottom: 0;
  }
    h2.author { 
    font-size: 1.25em;
    font-family: Open Sans;
    text-align: right;
    margin: 0 0 0 0;
    font-weight: 300; color:#266871; 
  }
  h3.date { 
    text-align: right;
    font-size: 1em;
    font-family: Open Sans;
    margin: 0 0 0 0;
    font-weight: 300; font-style: normal;
  }
  ul { list-style-type: round;}
  ol { list-style-type: decimal;}
  ul, ol {
    margin: 10px 10px 10px 80px;
  }
  li { text-align: left; }
  q { quotes: "“" "”" "‘" "’"; }
  blockquote { 
    margin-top: 1.333em;
    padding-top: 1.333em;
    padding-bottom: 1.333em; 
    padding-left: 2em;
    padding-right: 2em;
    font-style: italic;
    text-align: right;
    border-right: 6px solid #b8463d;
    background-color: #f2f2f2;
  }
  a:link {color:#266871; text-decoration: none;}      /* unvisited link */
  a:visited {color:#266871; text-decoration: none;}  /* visited link */
  a:hover {color:#569ca6;}  /* mouse over link */
  a:active {color:#3e7f89;}  /* selected link */

  /* Figures are displayed full-page, with the caption on
     top of the image/video */
  figure {
    background-color: transparent;
    overflow: visible;
  }
  img:first-of-type {
    margin-left: -80px;
    margin-top: -120px;
    position:absolute;
    width: 800px;
    height: 600px;
    top: 0;
    left: 0;
    z-index: -1;
  }
  figure > img {
    width: 800px !important;
    height: 600px !important;
    margin-left: -80px;
    margin-top: -120px;
  }
  figcaption {
    margin: 70px;
  }
  footer {
    position: absolute;
    bottom: 0;
    width: 100%;
    padding: 40px;
    text-align: right;
    background-color: #F3F4F8;
    border-top: 1px solid #CCC;
  }

  /* Transition effect */
  /* Feel free to change the transition effect for original
     animations. See here:
     https://developer.mozilla.org/en/CSS/CSS_transitions
     How to use CSS3 Transitions: */
  section {
      -moz-transition: left 200ms ease-out 0s;
      -webkit-transition: left 200ms ease-out 0s;
      -ms-transition: left 200ms ease-out 0s;
      transition: left 200ms ease-out 0s;
  }

  /* Before */
  section { 

    width: 640px;
    position: absolute;
    height:360px;
    top: 50%; left: 50%;
    margin-left: -320px; margin-top: -180px;
    vertical-align: middle;
    left: -150%; }
  /* Now */
  section[aria-selected] { 
    /* 16:9 640x360 */
    width: 640px;
    position: absolute;
    height:360px;
    top: 50%; left: 50%;
    margin-left: -320px; margin-top: -180px;
    vertical-align: middle;
    display: inline-block;
  }
  /* After */
  section[aria-selected] ~ section { 

    width: 640px;
    position: absolute;
    height:360px;
    top: 50%; left: 50%;
    margin-left: -320px; margin-top: -180px;
    vertical-align: middle;
    left: +150%; 
  }

  /* Incremental elements */

  /* By default, visible */
  .incremental > * { opacity: 1; }

  /* The current item */
  .incremental > *[aria-selected] { color: #b8913d; opacity: 1; font-weight: 500;}

  /* The items to-be-selected */
  .incremental > *[aria-selected] ~ * { opacity: 0.3; }

  /*logos*/
  #logos_div {
    position: absolute;
    
  }
  #ohnoseq_logo_div {}
  #ohnoseq_logo {
    /*6.132867133*/
    height: 20px; width: 123px;
    top:570px;
    left: 730px;
    position: relative;
  }
  #era7_logo_div {}
  #era7_logo {
    /*4.866071429*/
    height: 20px; width: 97px;
    position: relative;
    top: 540px;
    left: 755px;
  }
  #intercrossing_logo {
    /*1.236979167*/
    height: 64px; width: 80px;
    position: relative;  
    top:45px;
    left: 780px;
  }
</style>
</head>
<body>
<section>
  <h1 class="title">the cloud?</h1>
  <h2 class="author"><script type="text/javascript">
                     <!--
                     h='&#x6f;&#104;&#110;&#x6f;&#x73;&#x65;&#x71;&#x75;&#x65;&#110;&#x63;&#x65;&#x73;&#46;&#x63;&#x6f;&#x6d;';a='&#64;';n='&#x65;&#112;&#x61;&#114;&#x65;&#106;&#x61;&#116;&#x6f;&#98;&#x65;&#x73;';e=n+a+h;
                     document.write('<a h'+'ref'+'="ma'+'ilto'+':'+e+'">'+'Eduardo Pareja-Tobes'+'<\/'+'a'+'>');
                     // -->
                     </script><noscript>&#x45;&#100;&#x75;&#x61;&#114;&#100;&#x6f;&#32;&#80;&#x61;&#114;&#x65;&#106;&#x61;&#x2d;&#84;&#x6f;&#98;&#x65;&#x73;&#32;&#40;&#x65;&#112;&#x61;&#114;&#x65;&#106;&#x61;&#116;&#x6f;&#98;&#x65;&#x73;&#32;&#x61;&#116;&#32;&#x6f;&#104;&#110;&#x6f;&#x73;&#x65;&#x71;&#x75;&#x65;&#110;&#x63;&#x65;&#x73;&#32;&#100;&#x6f;&#116;&#32;&#x63;&#x6f;&#x6d;&#x29;</noscript></h2>
  <h3 class="date">today</h3>
</section>
<div id="logos_div">
  <div id="ohnoseq_logo_div">
    <a href="http://ohnosequences.com">
      <img id="ohnoseq_logo" src="ohnoseq-logo.png">
    </a>
  </div>
  </div>
  <div id="era7_logo_div">
    <a href="http://era7bioinformatics.com">
      <img id="era7_logo" src="era7-logo.png">
    </a>
  </div>
  <div id="intercrossing_logo_div">
    <a href="http://intercrossing.wikispaces.com">
      <img id="intercrossing_logo" src="intercrossing-logo.png">
    </a>
  </div>
</div> 
<section class="slide level2">

<h4 id="talk-outline">talk outline</h4>
<p><br\></p>
<p>the <strong>cloud</strong>: what it is, some general implications.</p>
<p>an intro to <strong>EC2</strong> and <strong>S3</strong>: the two canonical services which started all this cloud thing</p>
</section>
<section id="what-cloud-means" class="titleslide slide level1"><h1>what cloud means</h1></section><section id="key-features" class="slide level2">
<h1>4 key features</h1>
<ol class="incremental" type="1">
<li>on-demand</li>
<li>remote/distributed</li>
<li>scalable</li>
<li>measurable</li>
</ol>
</section><section id="on-demand" class="slide level2">
<h1>1. on-demand</h1>
<p>ability to provision resources without <em>human</em> interaction:</p>
<ul>
<li><strong>API</strong>: <strong>A</strong>pplication <strong>P</strong>rogrammer <strong>I</strong>nterface</li>
</ul>
</section><section class="slide level2">

<h3 id="api-what---example">API <em>what?</em> - example:</h3>
<pre class="sourceCode scala"><code class="sourceCode scala"><span class="co">// fake code:</span>
<span class="co">// I want a server</span>
<span class="kw">val</span> server = cloud.<span class="fu">createInstance</span>
<span class="co">// now, create a file there</span>
<span class="kw">val</span> content = <span class="st">&quot;hi cloud!&quot;</span>
<span class="kw">val</span> file = cloud.<span class="fu">createFile</span>(content)</code></pre>
</section><section id="remote-access" class="slide level2">
<h1>2. remote access</h1>
<p>Ability to act on resources from any point inside a <em>network</em></p>
<ul>
<li>actions defined by <strong>API</strong>s</li>
<li><strong>authentication</strong> mechanisms</li>
</ul>
</section><section class="slide level2">

<h3 id="example-again">example again:</h3>
<pre class="sourceCode scala"><code class="sourceCode scala"><span class="co">// restart that server</span>
server.<span class="fu">restart</span>
<span class="co">// get rid of that file</span>
file.<span class="fu">delete</span></code></pre>
</section><section class="slide level2">

<h3 id="how-all-this-works">how all this works?</h3>
<p>you need to represent actions as communication between members of the <strong>network</strong>. How? standard <strong>internet</strong> protocols and conventions</p>
</section><section class="slide level2">

<p>Two key aspects here:</p>
<ul class="incremental">
<li><strong>communication</strong> between: you and the service, different components, …</li>
<li><strong>authentication</strong> me is me, the service is the service</li>
</ul>
</section><section class="slide level2">

<h3 id="communication">communication</h3>
<ul>
<li>network protocols: <strong>HTTP/S</strong></li>
<li>services expose HTTP-based APIs at endpoints (URLs)</li>
</ul>
</section><section class="slide level2">

<h3 id="communication-ii">communication II</h3>
<p>actions are mapped to requests</p>
<ul>
<li>at particular <strong>URLs</strong>: <code>http://cloud.com/datatype/action</code></li>
<li>with particular <strong>params</strong>: <code>POST</code>, <code>GET</code>, <code>?public=true</code></li>
</ul>
</section><section class="slide level2">

<h3 id="authentication">authentication</h3>
<p>actions are signed using <strong>asymmetric-key</strong> encryption.</p>
<p>normally using <a href="https://en.wikibooks.org/wiki/Cryptography/RSA">RSA</a></p>
</section><section class="slide level2">

<h3 id="authentication-ii">authentication II</h3>
<ul>
<li><strong>private</strong> key: <em>encrypt/sign</em></li>
<li><strong>public</strong> key: <em>decrypt/verify</em></li>
</ul>
</section><section class="slide level2">

<h3 id="authentication-iii">authentication III</h3>
<ul>
<li>the <strong>client</strong> signs requests</li>
<li>the <strong>service</strong> verifies requests</li>
</ul>
</section><section class="slide level2">

<h3 id="again-standards">again, standards</h3>
<ul class="incremental">
<li><strong>transport</strong>: rely on standard network protocols: <strong><code>HTTP/S</code></strong>, <strong><code>SSH</code></strong></li>
<li>same for <strong>authentication</strong> and encryption: <strong><code>SSL</code></strong>, <strong><code>RSA</code></strong></li>
</ul>
</section><section class="slide level2">

<h3 id="distributed-i">distributed I</h3>
<pre class="sourceCode scala"><code class="sourceCode scala"><span class="co">// send a HTTP request </span>
<span class="co">// to a service endpoint:</span>
<span class="co">// http://machines.cloud.com</span>
server.<span class="fu">restart</span>
<span class="co">// this request is signed </span>
<span class="co">// for example, using RSA</span></code></pre>
</section><section class="slide level2">

<h3 id="distributed-ii">distributed II</h3>
<p>after <code>server.restart</code>, at <em>some</em> point in the <strong>future</strong>, the cloud service <strong>restarts</strong> your server. Or <strong>not</strong>.</p>
</section><section class="slide level2">

<h3 id="distributed-iii">distributed III</h3>
<ul>
<li>welcome to <strong>distributed</strong> systems!</li>
</ul>
<p><br /> more on the <a href="">cloud arch</a> session.</p>
</section><section id="scalable" class="slide level2">
<h1>3. scalable</h1>
<p><strong>boundless</strong> (in principle) provisioning and release of <strong>resources</strong></p>
</section><section class="slide level2">

<h3 id="resources">resources?</h3>
<ul class="incremental">
<li>servers</li>
<li>storage</li>
<li>databases</li>
<li>message queues</li>
<li>…</li>
</ul>
</section><section class="slide level2">

<h3 id="example">example</h3>
<pre class="sourceCode scala"><code class="sourceCode scala"><span class="co">// got data today! let&#39;s do some stuff</span>
<span class="kw">val</span> servers = cloud.<span class="fu">instances</span>(<span class="dv">100</span>)
<span class="co">// this takes less than 2h</span>
servers analyze data
<span class="co">// so release resources after</span>
<span class="fu">in</span> (<span class="dv">2</span> h) { servers.<span class="fu">terminate</span> }</code></pre>
</section><section class="slide level2">

<h3 id="importance">importance</h3>
<ul>
<li><strong>grow</strong> and <strong>reduce</strong> your infrastructure according to <strong>state</strong></li>
<li>and do it <strong>automatically</strong></li>
</ul>
</section><section class="slide level2">

<h3 id="for-example">for example</h3>
<ul>
<li>web apps → traffic</li>
<li>data analysis → availability, size</li>
<li>…</li>
</ul>
</section><section id="measurable" class="slide level2">
<h1>4. measurable</h1>
<p>the <strong>service</strong> exposes information about <strong>itself</strong></p>
<ul class="incremental">
<li>service use → <em>cost</em></li>
<li>resources → <em>state</em></li>
</ul>
</section><section class="slide level2">

<h3 id="cost-model">cost model</h3>
<blockquote>
<p>pay for what you use</p>
</blockquote>
</section><section class="slide level2">

<h3 id="cost-model-1">cost model</h3>
<p>The single most disrupting trait of cloud computing.</p>
<p>Making infrastructure an <a href="https://en.wikipedia.org/wiki/Intangible_good">intangible</a> <a href="https://en.wikipedia.org/wiki/Commodity">commodity</a> is huge!</p>
</section><section class="slide level2">

</section>
<section id="variants" class="titleslide slide level1"><h1>variants</h1></section><section id="terminology" class="slide level2">
<h1>terminology</h1>
<p>Based on what you get, cloud services classified into:</p>
<p><strong>XaaS</strong>: <strong>X</strong> <strong>a</strong>s <strong>a</strong> <strong>S</strong>ervice</p>
</section><section id="basic-kinds" class="slide level2">
<h1>3 basic kinds</h1>
<ul class="incremental">
<li><em>IaaS</em> Infrastructure</li>
<li><em>PaaS</em> Platform</li>
<li><em>SaaS</em> Software –cloud?</li>
</ul>
</section><section class="slide level2">

<h3 id="the-abstraction-layer">the abstraction layer</h3>
<p>From abstract to concrete: you run <em>software</em> on top a <em>platform</em>, which needs some <em>infrastructure</em>.</p>
<ul class="incremental">
<li><strong>S</strong>aaS → <strong>P</strong>aaS → <strong>I</strong>aaS</li>
</ul>
</section><section class="slide level2">

<h3 id="more-exotic-terminology">more exotic terminology</h3>
<ul class="incremental">
<li><em>DaaS</em> Data</li>
<li><em>NaaS</em> Network</li>
<li><em>FaaS</em> Food :)</li>
</ul>
</section>
<section id="iaas" class="titleslide slide level1"><h1>IaaS</h1></section><section class="slide level2">

<h3 id="what">what?</h3>
<p>when you get <em>raw</em> stuff. Think of compute power, data storage, networking, …</p>
<p>Basically created by <strong>AWS</strong> with <strong>S3</strong> and <strong>EC2</strong>.</p>
</section><section class="slide level2">

<h3 id="providers">providers?</h3>
<ul class="incremental">
<li><strong>AWS</strong> <em>the real thing</em></li>
<li><strong>RackSpace</strong> <em>good support!</em></li>
<li><strong>Joyent</strong> <em>nice, niche player</em></li>
<li><strong>Azure</strong> <em>Windows stuff</em></li>
<li><strong>Google</strong> <em>??</em></li>
</ul>
</section><section class="slide level2">

<p>I will focus on two basic things, and the available options within the <strong>AWS</strong> offering:</p>
<ul>
<li><strong>compute</strong> machines → EC2</li>
<li><strong>storage</strong> object storage → S3</li>
</ul>
</section><section id="compute" class="slide level2">
<h1>compute</h1>
<p><strong>servers</strong> as a service. You choose your configuration:</p>
<ul>
<li><em>OS</em> Linux, Windows, …</li>
<li><em>hardware</em> RAM, CPU, …</li>
</ul>
</section><section class="slide level2">

<h3 id="ec2">EC2</h3>
<p>You instantiate <strong>instances</strong> from machine images called <strong>AMI</strong>s.</p>
<p>choose from a predefined set of <strong>hardware confs</strong>, called <a href="https://aws.amazon.com/en/ec2/instance-types/">instance types</a></p>
</section><section class="slide level2">

<h3 id="where">where?</h3>
<p>A set of <strong>regions</strong> (EU, US, …) further divided into <strong>availability zones</strong>.</p>
</section><section class="slide level2">

<h3 id="how">how?</h3>
<p>Make <strong>API</strong> calls from <em>anywhere</em> to <strong>region</strong>-specific service <strong>endpoints</strong></p>
</section><section class="slide level2">

<h3 id="ec2-scalability">EC2 scalability</h3>
<ul class="incremental">
<li>instance number limit: <em>∞</em></li>
<li>image number limit: <em>∞</em></li>
<li>create/kill instances: <em>~2min</em></li>
</ul>
</section><section class="slide level2">

<h3 id="ec2-pricing">EC2 pricing</h3>
<p>pay per <strong>hour</strong>, in different ways</p>
<ul>
<li>book capacity</li>
<li>bid</li>
<li>I want it now!</li>
</ul>
</section><section class="slide level2">

<h3 id="ec2-extras">EC2 extras</h3>
<p>A lot of bells and whistles around:</p>
<ul>
<li><a href="https://aws.amazon.com/en/autoscaling">Auto Scaling</a> instance groups</li>
<li><a href="https://aws.amazon.com/ec2/en/spot-instances">Spot Instances</a> a bid market!</li>
<li><a href="https://aws.amazon.com/en/cloudwatch">CloudWatch</a> monitoring</li>
<li>…</li>
</ul>
</section><section id="object-storage" class="slide level2">
<h1>object storage</h1>
<ul>
<li>put/get <strong>objects</strong></li>
<li>they live inside <strong>buckets</strong></li>
</ul>
<p><br \> think of a remote <em>filesystem</em> with <em>one folder level</em>.</p>
</section><section id="object-storage-ii" class="slide level2">
<h1>object storage II</h1>
<ul class="incremental">
<li><strong>simple</strong></li>
<li>but, <strong>useful?</strong></li>
<li>yes! lose <em>features</em>, get <em>scalability</em></li>
</ul>
</section><section class="slide level2">

<h3 id="s3">S3</h3>
<p>The dawn of <strong>AWS</strong>: launched in <em>2006</em>. Created the concept of object storage.</p>
<p>Heavily used by Amazon itself. And by <strong>you</strong>, too! –<em>dropbox</em></p>
</section><section class="slide level2">

<h3 id="where-1">where?</h3>
<ul>
<li><strong>Buckets</strong> live inside one <strong>region</strong></li>
<li><strong>Objects</strong> are stored <strong>replicated</strong> across several <em>zones</em>, then across several <em>datacenters</em>, then across several <em>servers</em></li>
</ul>
</section><section class="slide level2">

<h3 id="how-1">how?</h3>
<p>Make <strong>API</strong> calls from <em>anywhere</em> to <strong>region</strong>-specific service <strong>endpoints</strong></p>
</section><section class="slide level2">

<h3 id="s3-scalability">S3 scalability</h3>
<ul class="incremental">
<li>object number limit: <em>∞</em></li>
<li>total storage limit: <em>∞</em></li>
<li>durability: <em>99.999999999%</em></li>
<li><em>global</em> service throughput: <em>∞</em></li>
</ul>
</section><section class="slide level2">

<h3 id="s3-pricing">S3 pricing</h3>
<ul class="incremental">
<li><strong>pay</strong> for what you <strong>use</strong></li>
<li><strong>cheap</strong>: 0<strong>.</strong>10$/GB/year</li>
<li>again, <strong>different</strong> options</li>
</ul>
</section><section class="slide level2">

<h3 id="questions">questions!</h3>
<p>and hopefully <strong>answers</strong>.</p>
<p>I think you should try <em>:)</em></p>
</section>
<!-- {{{{ dzslides core
#
#
#     __  __  __       .  __   ___  __
#    |  \  / /__` |    | |  \ |__  /__`
#    |__/ /_ .__/ |___ | |__/ |___ .__/ core :€
#
#
# The following block of code is not supposed to be edited.
# But if you want to change the behavior of these slides,
# feel free to hack it!
#
-->

<div id="progress-bar"></div>

<!-- Default Style -->
<style>
  * { margin: 0; padding: 0; -moz-box-sizing: border-box; -webkit-box-sizing: border-box; box-sizing: border-box; }
  details { display: none; }
  body {
    width: 800px; height: 600px;
    margin-left: -400px; margin-top: -300px;
    position: absolute; top: 50%; left: 50%;
    overflow: hidden;
  }
  section {
    position: absolute;
    pointer-events: none;
    width: 100%; height: 100%;
  }
  section[aria-selected] { pointer-events: auto; }
  html { overflow: hidden; }
  body { display: none; }
  body.loaded { display: block; }
  .incremental {visibility: hidden; }
  .incremental[active] {visibility: visible; }
  #progress-bar{
    bottom: 0;
    position: absolute;
    -moz-transition: width 400ms linear 0s;
    -webkit-transition: width 400ms linear 0s;
    -ms-transition: width 400ms linear 0s;
    transition: width 400ms linear 0s;
  }
  figure {
    width: 100%;
    height: 100%;
  }
  figure > * {
    position: absolute;
  }
  figure > img, figure > video {
    width: 100%; height: 100%;
  }
</style>

<script>
  var Dz = {
    remoteWindows: [],
    idx: -1,
    step: 0,
    slides: null,
    progressBar : null,
    params: {
      autoplay: "1"
    }
  };

  Dz.init = function() {
    document.body.className = "loaded";
    this.slides = $$("body > section");
    this.progressBar = $("#progress-bar");
    this.setupParams();
    this.onhashchange();
    this.setupTouchEvents();
    this.onresize();
  }
  
  Dz.setupParams = function() {
    var p = window.location.search.substr(1).split('&');
    p.forEach(function(e, i, a) {
      var keyVal = e.split('=');
      Dz.params[keyVal[0]] = decodeURIComponent(keyVal[1]);
    });
  // Specific params handling
    if (!+this.params.autoplay)
      $$.forEach($$("video"), function(v){ v.controls = true });
  }

  Dz.onkeydown = function(aEvent) {
    // Don't intercept keyboard shortcuts
    if (aEvent.altKey
      || aEvent.ctrlKey
      || aEvent.metaKey
      || aEvent.shiftKey) {
      return;
    }
    if ( aEvent.keyCode == 37 // left arrow
      || aEvent.keyCode == 38 // up arrow
      || aEvent.keyCode == 33 // page up
    ) {
      aEvent.preventDefault();
      this.back();
    }
    if ( aEvent.keyCode == 39 // right arrow
      || aEvent.keyCode == 40 // down arrow
      || aEvent.keyCode == 34 // page down
    ) {
      aEvent.preventDefault();
      this.forward();
    }
    if (aEvent.keyCode == 35) { // end
      aEvent.preventDefault();
      this.goEnd();
    }
    if (aEvent.keyCode == 36) { // home
      aEvent.preventDefault();
      this.goStart();
    }
    if (aEvent.keyCode == 32) { // space
      aEvent.preventDefault();
      this.toggleContent();
    }
    if (aEvent.keyCode == 70) { // f
      aEvent.preventDefault();
      this.goFullscreen();
    }
  }

  /* Touch Events */

  Dz.setupTouchEvents = function() {
    var orgX, newX;
    var tracking = false;

    var db = document.body;
    db.addEventListener("touchstart", start.bind(this), false);
    db.addEventListener("touchmove", move.bind(this), false);

    function start(aEvent) {
      aEvent.preventDefault();
      tracking = true;
      orgX = aEvent.changedTouches[0].pageX;
    }

    function move(aEvent) {
      if (!tracking) return;
      newX = aEvent.changedTouches[0].pageX;
      if (orgX - newX > 100) {
        tracking = false;
        this.forward();
      } else {
        if (orgX - newX < -100) {
          tracking = false;
          this.back();
        }
      }
    }
  }

  /* Adapt the size of the slides to the window */

  Dz.onresize = function() {
    var db = document.body;
    var sx = db.clientWidth / window.innerWidth;
    var sy = db.clientHeight / window.innerHeight;
    var transform = "scale(" + (1/Math.max(sx, sy)) + ")";

    db.style.MozTransform = transform;
    db.style.WebkitTransform = transform;
    db.style.OTransform = transform;
    db.style.msTransform = transform;
    db.style.transform = transform;
  }


  Dz.getDetails = function(aIdx) {
    var s = $("section:nth-of-type(" + aIdx + ")");
    var d = s.$("details");
    return d ? d.innerHTML : "";
  }

  Dz.onmessage = function(aEvent) {
    var argv = aEvent.data.split(" "), argc = argv.length;
    argv.forEach(function(e, i, a) { a[i] = decodeURIComponent(e) });
    var win = aEvent.source;
    if (argv[0] === "REGISTER" && argc === 1) {
      this.remoteWindows.push(win);
      this.postMsg(win, "REGISTERED", document.title, this.slides.length);
      this.postMsg(win, "CURSOR", this.idx + "." + this.step);
      return;
    }
    if (argv[0] === "BACK" && argc === 1)
      this.back();
    if (argv[0] === "FORWARD" && argc === 1)
      this.forward();
    if (argv[0] === "START" && argc === 1)
      this.goStart();
    if (argv[0] === "END" && argc === 1)
      this.goEnd();
    if (argv[0] === "TOGGLE_CONTENT" && argc === 1)
      this.toggleContent();
    if (argv[0] === "SET_CURSOR" && argc === 2)
      window.location.hash = "#" + argv[1];
    if (argv[0] === "GET_CURSOR" && argc === 1)
      this.postMsg(win, "CURSOR", this.idx + "." + this.step);
    if (argv[0] === "GET_NOTES" && argc === 1)
      this.postMsg(win, "NOTES", this.getDetails(this.idx));
  }

  Dz.toggleContent = function() {
    // If a Video is present in this new slide, play it.
    // If a Video is present in the previous slide, stop it.
    var s = $("section[aria-selected]");
    if (s) {
      var video = s.$("video");
      if (video) {
        if (video.ended || video.paused) {
          video.play();
        } else {
          video.pause();
        }
      }
    }
  }

  Dz.setCursor = function(aIdx, aStep) {
    // If the user change the slide number in the URL bar, jump
    // to this slide.
    aStep = (aStep != 0 && typeof aStep !== "undefined") ? "." + aStep : ".0";
    window.location.hash = "#" + aIdx + aStep;
  }

  Dz.onhashchange = function() {
    var cursor = window.location.hash.split("#"),
        newidx = 1,
        newstep = 0;
    if (cursor.length == 2) {
      newidx = ~~cursor[1].split(".")[0];
      newstep = ~~cursor[1].split(".")[1];
      if (newstep > Dz.slides[newidx - 1].$$('.incremental > *').length) {
        newstep = 0;
        newidx++;
      }
    }
    this.setProgress(newidx, newstep);
    if (newidx != this.idx) {
      this.setSlide(newidx);
    }
    if (newstep != this.step) {
      this.setIncremental(newstep);
    }
    for (var i = 0; i < this.remoteWindows.length; i++) {
      this.postMsg(this.remoteWindows[i], "CURSOR", this.idx + "." + this.step);
    }
  }

  Dz.back = function() {
    if (this.idx == 1 && this.step == 0) {
      return;
    }
    if (this.step == 0) {
      this.setCursor(this.idx - 1,
                     this.slides[this.idx - 2].$$('.incremental > *').length);
    } else {
      this.setCursor(this.idx, this.step - 1);
    }
  }

  Dz.forward = function() {
    if (this.idx >= this.slides.length &&
        this.step >= this.slides[this.idx - 1].$$('.incremental > *').length) {
        return;
    }
    if (this.step >= this.slides[this.idx - 1].$$('.incremental > *').length) {
      this.setCursor(this.idx + 1, 0);
    } else {
      this.setCursor(this.idx, this.step + 1);
    }
  }

  Dz.goStart = function() {
    this.setCursor(1, 0);
  }

  Dz.goEnd = function() {
    var lastIdx = this.slides.length;
    var lastStep = this.slides[lastIdx - 1].$$('.incremental > *').length;
    this.setCursor(lastIdx, lastStep);
  }

  Dz.setSlide = function(aIdx) {
    this.idx = aIdx;
    var old = $("section[aria-selected]");
    var next = $("section:nth-of-type("+ this.idx +")");
    if (old) {
      old.removeAttribute("aria-selected");
      var video = old.$("video");
      if (video) {
        video.pause();
      }
    }
    if (next) {
      next.setAttribute("aria-selected", "true");
      var video = next.$("video");
      if (video && !!+this.params.autoplay) {
        video.play();
      }
    } else {
      // That should not happen
      this.idx = -1;
      // console.warn("Slide doesn't exist.");
    }
  }

  Dz.setIncremental = function(aStep) {
    this.step = aStep;
    var old = this.slides[this.idx - 1].$('.incremental > *[aria-selected]');
    if (old) {
      old.removeAttribute('aria-selected');
    }
    var incrementals = $$('.incremental');
    if (this.step <= 0) {
      $$.forEach(incrementals, function(aNode) {
        aNode.removeAttribute('active');
      });
      return;
    }
    var next = this.slides[this.idx - 1].$$('.incremental > *')[this.step - 1];
    if (next) {
      next.setAttribute('aria-selected', true);
      next.parentNode.setAttribute('active', true);
      var found = false;
      $$.forEach(incrementals, function(aNode) {
        if (aNode != next.parentNode)
          if (found)
            aNode.removeAttribute('active');
          else
            aNode.setAttribute('active', true);
        else
          found = true;
      });
    } else {
      setCursor(this.idx, 0);
    }
    return next;
  }

  Dz.goFullscreen = function() {
    var html = $('html'),
        requestFullscreen = html.requestFullscreen || html.requestFullScreen || html.mozRequestFullScreen || html.webkitRequestFullScreen;
    if (requestFullscreen) {
      requestFullscreen.apply(html);
    }
  }
  
  Dz.setProgress = function(aIdx, aStep) {
    var slide = $("section:nth-of-type("+ aIdx +")");
    if (!slide)
      return;
    var steps = slide.$$('.incremental > *').length + 1,
        slideSize = 100 / (this.slides.length - 1),
        stepSize = slideSize / steps;
    this.progressBar.style.width = ((aIdx - 1) * slideSize + aStep * stepSize) + '%';
  }
  
  Dz.postMsg = function(aWin, aMsg) { // [arg0, [arg1...]]
    aMsg = [aMsg];
    for (var i = 2; i < arguments.length; i++)
      aMsg.push(encodeURIComponent(arguments[i]));
    aWin.postMessage(aMsg.join(" "), "*");
  }
  
  function init() {
    Dz.init();
    window.onkeydown = Dz.onkeydown.bind(Dz);
    window.onresize = Dz.onresize.bind(Dz);
    window.onhashchange = Dz.onhashchange.bind(Dz);
    window.onmessage = Dz.onmessage.bind(Dz);
  }

  window.onload = init;
</script>


<script> // Helpers
  if (!Function.prototype.bind) {
    Function.prototype.bind = function (oThis) {

      // closest thing possible to the ECMAScript 5 internal IsCallable
      // function 
      if (typeof this !== "function")
      throw new TypeError(
        "Function.prototype.bind - what is trying to be fBound is not callable"
      );

      var aArgs = Array.prototype.slice.call(arguments, 1),
          fToBind = this,
          fNOP = function () {},
          fBound = function () {
            return fToBind.apply( this instanceof fNOP ? this : oThis || window,
                   aArgs.concat(Array.prototype.slice.call(arguments)));
          };

      fNOP.prototype = this.prototype;
      fBound.prototype = new fNOP();

      return fBound;
    };
  }

  var $ = (HTMLElement.prototype.$ = function(aQuery) {
    return this.querySelector(aQuery);
  }).bind(document);

  var $$ = (HTMLElement.prototype.$$ = function(aQuery) {
    return this.querySelectorAll(aQuery);
  }).bind(document);

  $$.forEach = function(nodeList, fun) {
    Array.prototype.forEach.call(nodeList, fun);
  }

</script>
<!-- vim: set fdm=marker: }}} -->
</body>
</html>
  </iframe>
</div>
<div id="controls">
  <button title="prev" id="back" onclick="Dz.back()">&#9664;</button>
  <button title="next" id="forward" onclick="Dz.forward()">&#9654;</button>
  <div id="rightcontrols">
    <input onchange="Dz.setCursor(this.value)" size="2" id="slideidx" value="0" />/<span id="slidecount">...</span>
    <button title="Go fullscreen or open in a new window" id="fullscreen" onclick="Dz.goFullscreen()">&#8689;</button>
  </div>
</div>

<style>
  html { height: 100%;}
  body {
    margin: 0;
    background-color: black;
    height: 100%;
    width: 100%;
  }
  #slides, #controls {
    left: 0;
    position: absolute;
    right: 0;
  }
  #controls {
    color: white;
    font-family: monospace;
    height: 30px;
    line-height: 30px;
    padding: 5px;
  }
  #slides {
    bottom: 40px;
    top: 0;
  }
  iframe {
    border: none;
    background-color: white;
    height: 480;
    width: 360;
  }
  #controls {
    bottom: 0;
    float: right;
    font-size: 13px;
    text-align: center;
  }
  #controls button[disabled] {color: #333;}
  button {
    background-color: transparent;
    border: none;
    cursor: pointer;
    color: #bbb;
    padding: 0;
    font-size: 20px;
    line-height: 100%;
    -webkit-user-select: none;
    -khtml-user-select: none;
    -moz-user-select: none;
    -o-user-select: none;
    user-select: none;
    position: relative;
  }
  button:hover {
    color: white;
  }
  button:active {
    top: 1px;
    left: 1px;
  }
  #slideidx {
    border: none;
    background-color: rgba(255, 255, 255, 0.2);
    color: white;
    text-align: center;
  }
  #rightcontrols * { vertical-align: middle; }
  #rightcontrols {
    bottom: 4px;
    position: absolute;
    top: 4px;
    right: 10px;
  }
  #fullscreen {-moz-transform: scaleX(-1);-webkit-transform: scaleX(-1);-o-transform: scaleX(-1);-ms-transform: scaleX(-1);transform: scaleX(-1);}
</style>

<script>
  var Dz = {
    view: null,
    url: null,
    idx: 1,
    count: null,
    iframe: null
  };
  
  Dz.init = function() {
    this.loadIframe();
  }
  
  Dz.onkeydown = function(aEvent) {
    // Don't intercept keyboard shortcuts
    if (aEvent.altKey
      || aEvent.ctrlKey
      || aEvent.metaKey
      || aEvent.shiftKey) {
      return;
    }
    if ( aEvent.keyCode == 37 // left arrow
      || aEvent.keyCode == 38 // up arrow
      || aEvent.keyCode == 33 // page up
    ) {
      aEvent.preventDefault();
      this.back();
    }
    if ( aEvent.keyCode == 39 // right arrow
      || aEvent.keyCode == 40 // down arrow
      || aEvent.keyCode == 34 // page down
    ) {
      aEvent.preventDefault();
      this.forward();
    }
    if (aEvent.keyCode == 35) { // end
      aEvent.preventDefault();
      this.goEnd();
    }
    if (aEvent.keyCode == 36) { // home
      aEvent.preventDefault();
      this.goStart();
    }
    if (aEvent.keyCode == 32) { // space
      aEvent.preventDefault();
      this.toggleContent();
    }
    if (aEvent.keyCode == 70) { // f
      aEvent.preventDefault();
      this.goFullscreen();
    }
  }
  
  Dz.onmessage = function(aEvent) {
    if (aEvent.source === this.view) {
      var argv = aEvent.data.split(" "), argc = argv.length;
      argv.forEach(function(e, i, a) { a[i] = decodeURIComponent(e) });
      if (argv[0] === "CURSOR" && argc === 2) {
        var cursor = argv[1].split(".");
        this.idx = ~~cursor[0];
        this.step = ~~cursor[1];
        $("#slideidx").value = this.idx;
        $("#back").disabled = this.idx == 1;
        $("#forward").disabled = this.idx == this.count;
      }
      if (argv[0] === "REGISTERED" && argc === 3) {
        $("#slidecount").innerHTML = this.count = argv[2];
        document.title = argv[1];
      }
    }
  }
  
  /* Get url from hash or prompt and store it */
  
  Dz.getUrl = function() {
    var u = window.location.hash.split("#")[1];
    if (!u) {
      u = window.prompt("What is the URL of the slides?");
      if (u) {
        window.location.hash = u.split("#")[0];
        return u;
      }
      u = "<style>body{background-color:white;color:black}</style>";
      u += "<strong>ERROR:</strong> No URL specified.<br>";
      u += "Try<em>: " + document.location + "#yourslides.html</em>";
      u = "data:text/html," + encodeURIComponent(u);
    }
    return u;
  }
  
  Dz.loadIframe = function() {
    this.iframe = $("iframe");
    this.iframe.src = this.url = this.getUrl();
    this.iframe.onload = function() {
      Dz.view = this.contentWindow;
      Dz.postMsg(Dz.view, "REGISTER");
    }
  }
  
  Dz.toggleContent = function() {
    this.postMsg(this.view, "TOGGLE_CONTENT");
  }
  
  Dz.onhashchange = function() {
    this.loadIframe();
  }
  
  Dz.back = function() {
    this.postMsg(this.view, "BACK");
  }

  Dz.forward = function() {
    this.postMsg(this.view, "FORWARD");
  }

  Dz.goStart = function() {
    this.postMsg(this.view, "START");
  }

  Dz.goEnd = function() {
    this.postMsg(this.view, "END");
  }

  Dz.setCursor = function(aCursor) {
    this.postMsg(this.view, "SET_CURSOR", aCursor);
  }

  Dz.goFullscreen = function() {
    var requestFullscreen = this.iframe.requestFullscreen || this.iframe.requestFullScreen || this.iframe.mozRequestFullScreen || this.iframe.webkitRequestFullScreen;
    if (requestFullscreen) {
      requestFullscreen.apply(this.iframe);
    } else {
      window.open(this.url + "#" + this.idx, '', 'width=800,height=600,personalbar=0,toolbar=0,scrollbars=1,resizable=1');
    }
  }
  
  Dz.postMsg = function(aWin, aMsg) { // [arg0, [arg1...]]
    aMsg = [aMsg];
    for (var i = 2; i < arguments.length; i++)
      aMsg.push(encodeURIComponent(arguments[i]));
    aWin.postMessage(aMsg.join(" "), "*");
  }

  function init() {
    Dz.init();
    window.onkeydown = Dz.onkeydown.bind(Dz);
    window.onhashchange = Dz.loadIframe.bind(Dz);
    window.onmessage = Dz.onmessage.bind(Dz);
  }

  window.onload = init;
</script>


<script> // Helpers
  if (!Function.prototype.bind) {
    Function.prototype.bind = function (oThis) {

      // closest thing possible to the ECMAScript 5 internal IsCallable
      // function 
      if (typeof this !== "function")
      throw new TypeError(
        "Function.prototype.bind - what is trying to be fBound is not callable"
      );

      var aArgs = Array.prototype.slice.call(arguments, 1),
          fToBind = this,
          fNOP = function () {},
          fBound = function () {
            return fToBind.apply( this instanceof fNOP ? this : oThis || window,
                   aArgs.concat(Array.prototype.slice.call(arguments)));
          };

      fNOP.prototype = this.prototype;
      fBound.prototype = new fNOP();

      return fBound;
    };
  }

  var $ = (HTMLElement.prototype.$ = function(aQuery) {
    return this.querySelector(aQuery);
  }).bind(document);

</script>