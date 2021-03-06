---
outputs:
- Reveal
title: R Markdown & WordPress
hidden: true
layout: list
weight: 1
output: hugodown::md_document
countdown: true
rmd_hash: 7f271775f150fbfa

---

WordPress
=========

------------------------------------------------------------------------

Why use WordPress?
==================

-   Clicking to design the interface

-   Internationalization

-   Open Source

------------------------------------------------------------------------

Why NOT use WordPress
=====================

-   Performance?

-   Security?

If you use WordPress, read the docs.

------------------------------------------------------------------------

Do you use WordPress?
=====================

------------------------------------------------------------------------

Workarounds for no WordPress
============================

-   Use a subdomain for your R Markdown blog, linked from your main WordPress website.

-   [Netlify CMS](https://www.netlifycms.org/) and other CMS as an user-friendly interface on static websites (like Hugo).

------------------------------------------------------------------------

Now, Rmd and WordPress!
=======================

-   [`knitr::knit2wp()`](https://rdrr.io/pkg/knitr/man/knit2wp.html) is now too dated (it uses `RCurl` and `XML`)

-   I made a package using WordPress dot org API!

-   Bob Rudis' package for WordPress dot com API!

So your choice is between a too old tool and WIP packages. :joy: :sob:

------------------------------------------------------------------------

wordpress.com vs wordpress.org
==============================

-   Free/cheap wordpress.com: no plugin

-   Business wordpress.com: \$\$\$

-   Your own local server: efforts

-   Paid service hosting+domain name+ WordPress install: a few \$ a month

------------------------------------------------------------------------

JetPack
=======

Something you can add to any WordPress website (baked in dot com websites).

Free and paid features.

------------------------------------------------------------------------

Which API
=========

-   wordpress dot com =&gt; .com API

-   self-hosted without JetPack =&gt; .org API

-   self-hosted with JetPack =&gt; .com API

In my package, support for .org API, but .com coming.

------------------------------------------------------------------------

From Rmd to website
===================

Under the hood

{{<mermaid align="left">}}
graph LR;
    A[Rmd] --> |"R ( hugodown :package:, </br> downlit :package:) </br> & Pandoc"| B{md}
    B --> |"R (xml2 :package: ) </br> & Pandoc"| C[HTML]
    C --> |"WordPress"| D[HTML]
{{< /mermaid >}}

------------------------------------------------------------------------

From Rmd to website
===================

What you do

{{<mermaid align="left">}}
graph LR;
    A[Rmd] --> |":large_blue_circle: knit button"| B{md}
    B --> |"run wp_post()"| C[HTML]
    C --> |"Wait"| D[HTML]
{{< /mermaid >}}

------------------------------------------------------------------------

Setup for goodpress (0/3)
=========================

Have a WordPress website that's not a free/cheap plan from wordpress.com :wink:

[goodpress setup vignette](https://maelle.github.io/goodpress/articles/setup.html)

------------------------------------------------------------------------

Setup for goodpress (1/3)
=========================

-   Install the [Application Passwords plugin](https://wordpress.org/plugins/application-passwords/)

-   Edit [.htaccess](https://github.com/WordPress/application-passwords/wiki/Basic-Authorization-Header----Missing) (with a plugin?)

-   Create an user with limited rights, and an application password for them. Save secrets in `.Renviron`

------------------------------------------------------------------------

Setup for goodpress (2/3)
=========================

For R syntax highlighting :sparkles:

-   Find [my code.css](https://github.com/maelle/goodpress/blob/main/inst/css/code.css) and copy it to your clipboard.

-   From your WordPress admin dasbhoard, go to Appearance &gt; Customize &gt; Additional CSS. Paste the CSS there and click on publish.

------------------------------------------------------------------------

Setup for goodpress (3/3)
=========================

If you want to use MathJax for equations.

From WordPress interface go to Appearance &gt; Theme Editor. In `<head>` div of `header.php`, then save.

``` html
<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
```

------------------------------------------------------------------------

:mountain_railway: Time for a demo!

[Notes on the course website](/wordpress/demo/)

------------------------------------------------------------------------

Scientific Rmd Blog Checklist

-   [x] R Markdown
-   [x] Syntax highlighting (for R)
-   [x] Modern
-   [x] .bib
-   \[?\] Citation for posts (add it to all posts? WordPress theme?)
-   [x] Equations

------------------------------------------------------------------------

Sustainability
==============

goodpress:

<div class="highlight">

Maëlle Salmon

</div>

[Contributors welcome](https://github.com/maelle/goodpress/).

pressur:

<div class="highlight">

Bob Rudis

</div>

------------------------------------------------------------------------

Limitations?
============

-   WordPress limitations (performance? security? how to tweak a theme)

-   The R part is promising but not stable yet

------------------------------------------------------------------------

Further resources
=================

[Listed on the course website](/wordpress/further-resources/) :bookmark_tabs:

------------------------------------------------------------------------

Questions, comments?
====================

Write them in the pad!

------------------------------------------------------------------------

Time for a break :tropical_drink:
=================================

<!--html_preserve-->

<div id="timer_wordpress" class="countdown" style="top:100;left:0;" data-warnwhen="0">

<code class="countdown-time"><span class="countdown-digits minutes">05</span><span class="countdown-digits colon">:</span><span class="countdown-digits seconds">00</span></code>

</div>

<!--/html_preserve-->

