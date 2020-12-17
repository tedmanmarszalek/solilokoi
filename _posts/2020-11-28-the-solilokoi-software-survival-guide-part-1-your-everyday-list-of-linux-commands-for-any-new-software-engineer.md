---
ID: 127
post_title: 'The Solilokoi Software Survival Guide, Part 1: Your Everyday List of Linux Commands for Any New Software Engineer'
author: tedman.marszalek
post_excerpt: ""
layout: post
permalink: >
  https://solilokoi.com/the-solilokoi-software-survival-guide-part-1-your-everyday-list-of-linux-commands-for-any-new-software-engineer/
published: true
post_date: 2020-11-28 00:51:04
---
<!-- wp:paragraph -->
<p>When I first began my software engineering career, my sysadmin background was lacking. Beyond the basics, these are the top commands I utilize most often.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>grep</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>My oversimplified summary of grep is that it is a text parser. So first let's provide some text.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>echo "Thanks for reading solilokoi\n(This line is irrelevant)\nBest, solilokoi"</code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Thanks for reading solilokoi
(This line is irrelevant)
Best, solilokoi</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>The echo command generated this output, but what if some of it is irrelevant? For example, if it was a very long manuscript and you only needed to find excerpts based on relevant keywords. Try grepping:  </p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>echo "Thanks for reading solilokoi\n(This line is irrelevant)\nBest, solilokoi" | grep koi</code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Thanks for reading solilokoi
Best, solilokoi</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>There is so much noise in data files, so I always grep for relevant information. I also recommend installing a nice terminal like <a href="https://iterm2.com/" data-type="URL" data-id="https://iterm2.com/">iTerm2</a> with improved syntax highlighting. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>ps</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>The linux ps command is often useful to retrieve PIDs for applications currently running on the server. I always pair it with some relevant flags to format the result in a reasonable way.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ps ax</code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code>  PID   TT  STAT      TIME COMMAND
    1   ??  Ss    28:56.02 /sbin/launchd
   43   ??  Ss     1:17.37 /usr/sbin/syslogd
   44   ??  Ss     0:24.60 /usr/libexec/UserEventAgent (System)
 ......</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>Now that we have some generated output, we can grep for relvant results. This is an example for retrieving all python processes currently running: </p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ps ax | grep python</code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code>96670   ??  S      1:28.57 /Users/solilokoi/.pyenv/versions/3.9.0/bin/python /Applications/PyCharm.app/Contents/plugins/python/helpers/pydev/pydevconsole.py --mode=client --port=59354</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>The grep isolated a process (PID = 96670) associated with running my PyCharm IDE.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>kill</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Sometimes when troubleshooting applications running locally or on remote servers, I'll need to shutdown the process. For example, Processes may hang or require reboot after consuming too many resources. </p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>kill -9 &lt;PID&gt;</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>After grepping for a particular service, you can use the PID to shut it down forcefully. </p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>kill -9 96670</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>history</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>I forget really basic syntax constantly, so I am heavily reliant on retrieving my terminal history</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>history</code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code>...
10685  ls
10686  ll
10687  ps ax | grep python
10688  ps ax | grep java
...</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>This is another useful example for grepping the results: </p>
<!-- /wp:paragraph -->

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
<pre class="wp-block-code"><code>ln -s &lt;file-patch-path&gt; &lt;link-path-name&gt;</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>I often leverage links when referencing predefined common modules in terraform. Here is an example: </p>
<!-- /wp:paragraph --></div></div>
<!-- /wp:group -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ln -s ../common_pkg/dependency.tf common_pkg_dependency.tf</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>Thanks for reading my Linux command essentials! I will continue to edit and expand upon these 2 minute tutorials by providing TLDR code cheatsheets. Here is the first cheatsheet release for Everyday Linux: <a href="https://solilokoi.com/the-solilokoi-software-survival-cheatsheet-part-1-everyday-linux-commands/">Linux Cheatsheet</a>.</p>
<!-- /wp:paragraph -->