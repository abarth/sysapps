sysapps
=======

Repository for the W3C System Applications working group

Specifications
--------------

This repository contains the following specifications:

* http://abarth.github.com/sysapps/drafts/runtime.html
* http://abarth.github.com/sysapps/drafts/security.html
* http://abarth.github.com/sysapps/drafts/raw-sockets.html

Setup
-----

To use the Makefile in the drafts directory, you might want to set up Anolis:
* http://wiki.whatwg.org/wiki/Anolis

This wiki page contains useful information about how to author specifications:
* http://wiki.whatwg.org/wiki/Howto_spec

Workflow
--------

You should edit the ".src.html" version of each specification. When you're done
editing, run "make" to build the publishable version of the specification. You
can then commit and push changes as usual.

If you would like to publish your changes to the web site, run "make publish",
which will update the web site to the most recent version that you've pushed
to origin/master.
