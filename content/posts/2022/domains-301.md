---
title: "Updating Domains with Cloudways \u2022 301 Redirects"
author: Mr Ash
type: "post"
published: 2022-03-29
lastUpdated: 2022-11-05
url: "/updating-domains-with-cloudways-301-redirects/"
image: https://p146.p4.n0.cdn.getcloudapp.com/items/5zuLYnzQ/85fe852b-f508-4dff-a288-f94c643c6a3d.jpeg?v=30753a2d88d52f52620501ff93b956b3
categories: Web
tags:
  - Hosting
  - WordPress
---

So you’re updating domains, but what about your search rankings? I just did this myself and it wasn’t as hard as I expected.

*Disclaimer, if you need help, read [.htaccess file](https://support.cloudways.com/en/articles/5123922-what-can-i-do-with-an-htaccess-file) and [SSH setup](https://support.cloudways.com/en/articles/5119485-guide-to-connecting-to-your-application-using-ssh-sftp).*

## HTACCESS File

If you’re running a Content Delivery Network (CDN), turn off caching. For example, Cloudflare Dashboard > turn on development mode.

Next, connect to your server via SSH.

1. `ssh <username>@<ip>`
2. `nano .htaccess`
3. Copy the text below, replace the placeholder text.
4. Exit nano and save file, `CTRL + X` > `Y` > `ENTER`

```
<IfModule mod_rewrite.c>
  RewriteEngine On
  RewriteCond %{HTTP_HOST} ^olddomain.com$
  RewriteRule (.*)$ <https://newdomain.com/$1> [R=301,L]
</IfModule>
```

Done, you’ve added code to force the redirect of your new domain on all web pages.

## WordPress

Now reflect the new domain in WordPress.

Go to, Settings > General > WordPress Address (URL), Site Address (URL) and add your new domain to either both fields or site address.

![https://p146.p4.n0.cdn.getcloudapp.com/items/qGu7vGmO/515fb4f4-b80f-4701-bef6-1085aead738e.jpeg?v=c880891c70243b6ec38596bc3261be1c](https://p146.p4.n0.cdn.getcloudapp.com/items/qGu7vGmO/515fb4f4-b80f-4701-bef6-1085aead738e.jpeg?v=c880891c70243b6ec38596bc3261be1c)

Easy as, that’s it for WordPress.

## Cloudways

Now the server and WordPress application know about the changes, it’s over to your web host.

1. Cloudways > Application Management > Domain Management
2. Update Primary Domain to New Domain

![https://p146.p4.n0.cdn.getcloudapp.com/items/E0ugrv1E/b92d1c56-3a6c-4e8c-ba9a-b2ee86879a68.jpeg?v=26f0f0c7ac2390d135dbcfea3d26107a](https://p146.p4.n0.cdn.getcloudapp.com/items/E0ugrv1E/b92d1c56-3a6c-4e8c-ba9a-b2ee86879a68.jpeg?v=26f0f0c7ac2390d135dbcfea3d26107a)

If you’re stuck, reach out to the Cloudways support team, they’re super helpful. If you host with another provider, check their documentation for these steps.

## Search Engines

Lastly, to ensure your precious Search Rankings stay as they are, update your desired Search Engine Consoles.

1. For Google, Search Console > select your old domain.
2. Go to Settings > Change of address

For more see [How do I safely move or migrate my website to a new domain name?](https://www.sistrix.com/ask-sistrix/onpage-optimisation/how-do-i-safely-move-my-website-to-a-new-domain-name/)

Now repeat this for the other search engines such as Bing… or don’t. Hope this was helpful.