---
ID: 191
post_title: 'The Solilokoi Software Survival Cheatsheet, Part 1: Everyday Linux Commands'
author: tedman.marszalek
post_excerpt: ""
layout: post
permalink: >
  https://solilokoi.com/the-solilokoi-software-survival-cheatsheet-part-1-everyday-linux-commands/
published: true
post_date: 2020-11-28 01:11:36
---
<!-- wp:paragraph -->
<p>For the full tutorial, check out <a href="https://solilokoi.com/the-solilokoi-software-survival-guide-part-1-your-everyday-list-of-linux-commands-for-any-new-software-engineer/" data-type="URL" data-id="https://solilokoi.com/the-solilokoi-software-survival-guide-part-1-your-everyday-list-of-linux-commands-for-any-new-software-engineer/">Part 1 of the Survival Guide</a>. </p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>grep</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>echo "Thanks for reading solilokoi\n(This line is irrelevant)\nBest, solilokoi"</code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Thanks for reading solilokoi
(This line is irrelevant)
Best, solilokoi</code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code>echo "Thanks for reading solilokoi\n(This line is irrelevant)\nBest, solilokoi" | grep koi</code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Thanks for reading solilokoi
Best, solilokoi</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>ps</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ps ax | grep python</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>kill</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>kill -9 96670</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>history</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>history | grep python </code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code>...
10093  python3 --version
10231  pip3 install python-jenkins
10242  python3 job.py
10713  ps ax | grep python
...</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"fontSize":"large"} -->
<h2 class="has-large-font-size">ln</h2>
<!-- /wp:heading -->

<!-- wp:group -->
<div class="wp-block-group"><div class="wp-block-group__inner-container"><!-- wp:code -->
<pre class="wp-block-code"><code>ln -s &lt;file-patch-path> &lt;link-path-name></code></pre>
<!-- /wp:code --></div></div>
<!-- /wp:group -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ln -s ../common_pkg/dependency.tf common_pkg_dependency.tf</code></pre>
<!-- /wp:code -->