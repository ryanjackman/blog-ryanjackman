+++
title = "Hugo Setup"
weight = 0

[menu.main]
Name = "Hugo Setup"
parent = "Notes"
+++

This page is to help me remember how to operate this website.

---

To run the server publicly with livereload

`$ hugo server --bind "0.0.0.0" --baseURL "http://blog.ryanjackman.com"`

Access the page at http://blog.ryanjackman.com:1313/

---

Creating new pages

`$ hugo new section/post`

---

Symlink the hugo build folder to the public_html folder

`$ sudo ln -s /var/www/blog.ryanjackman.com/blog/public /var/www/blog.ryanjackman.com/public_html`
