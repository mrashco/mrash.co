---
id: 5310
title: Updating Domains with Cloudways | 301 Redirects
author: Mr Ash
type: "revision"
guid: https://mrash.co/?p=5310
url: "/?p=5310"
---

So you’re updating domains, but what about your search rankings? I just did this myself and it wasn’t as hard as I expected.

*Disclaimer, if you need help, read [.htaccess file](https://support.cloudways.com/en/articles/5123922-what-can-i-do-with-an-htaccess-file) and [SSH setup](https://support.cloudways.com/en/articles/5119485-guide-to-connecting-to-your-application-using-ssh-sftp).*

## 1. HTACCESS File

If you’re running a Content Delivery Network (CDN), turn off caching. For example, Cloudflare Dashboard &gt; turn on development mode.

Next, connect to your server via SSH.

1. `ssh <username>@<ip>`
2. `nano .htaccess`
3. Copy the text below, replace the placeholder text.
4. Exit nano and save file, `CTRL + X` &gt; `Y` &gt; `ENTER`

```
<pre class="wp-block-code">```
<IfModule mod_rewrite.c>
  RewriteEngine On
  RewriteCond %{HTTP_HOST} ^olddomain.com$
  RewriteRule (.*)$ <https://newdomain.com/$1> [R=301,L]
</IfModule>
```
```

Done, you’ve added code to force the redirect of your new domain on all web pages.

## 2. WordPress

Now reflect the new domain in WordPress.

Go to, Settings &gt; General &gt; WordPress Address (URL), Site Address (URL) and add your new domain to either both fields or site address.

<figure class="wp-block-image alignwide">![https://p146.p4.n0.cdn.getcloudapp.com/items/qGu7vGmO/515fb4f4-b80f-4701-bef6-1085aead738e.jpeg?v=c880891c70243b6ec38596bc3261be1c](https://p146.p4.n0.cdn.getcloudapp.com/items/qGu7vGmO/515fb4f4-b80f-4701-bef6-1085aead738e.jpeg?v=c880891c70243b6ec38596bc3261be1c)</figure>Easy as, that’s it for WordPress.

## 3. Cloudways

Now the server and WordPress application know about the changes, it’s over to your web host.

1. Cloudways &gt; Application Management &gt; Domain Management
2. Update Primary Domain to New Domain

<figure class="wp-block-image alignwide">![https://p146.p4.n0.cdn.getcloudapp.com/items/E0ugrv1E/b92d1c56-3a6c-4e8c-ba9a-b2ee86879a68.jpeg?v=26f0f0c7ac2390d135dbcfea3d26107a](https://p146.p4.n0.cdn.getcloudapp.com/items/E0ugrv1E/b92d1c56-3a6c-4e8c-ba9a-b2ee86879a68.jpeg?v=26f0f0c7ac2390d135dbcfea3d26107a)</figure>If you’re stuck, reach out to the Cloudways support team, they’re super helpful. If you host with another provider, check their documentation for these steps.

## 4. Search Engines

Lastly, to ensure your precious Search Rankings stay as they are, update your desired Search Engine Consoles.

1. For Google, Search Console &gt; select your old domain.
2. Go to Settings &gt; Change of address

For more see [How do I safely move or migrate my website to a new domain name?](https://www.sistrix.com/ask-sistrix/onpage-optimisation/how-do-i-safely-move-my-website-to-a-new-domain-name/)

Now repeat this for the other search engines such as Bing… or don’t. Hope this was helpful.