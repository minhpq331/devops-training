# Module 6: Setup a domain

In this module, you will learn how to set up a domain for your server. A domain is a human-readable address that points to your server's IP address. It's easier to remember a domain name than an IP address.

## Requirements

Our goal in this module is to register a domain and point it to our server's IP address. Despite the domain registrar you choose, the steps to set up a domain and manage DNS settings are similar.

## Instructions

1. You can buy a domain from a domain registrar like Namecheap, GoDaddy, Matbao or Cloudflare. You can also use a free domain from Freenom or other services, as long as they provide full control over the DNS settings.
2. We will use Cloudflare as DNS management provider. Despite the domain registrar you choose, you can use Cloudflare as a DNS management provider as long as your registrar allow you to change Nameserver (NS) records. Cloudflare is free and provides a lot of features like DNS caching, DDoS protection, Proxy and SSL. Signup for a free account and add your domain to Cloudflare.
3. Follow the instructions from Cloudflare to point your domain Name Server (NS) to Cloudflare's NS.
4. Wait for the DNS propagation to complete. It can take up to 24 hours for the DNS changes to take effect.
5. Add an A record on Cloudflare to point your domain to your server's IP address. Try to access your backend and frontend application using the domain name.

## Important notes

- Learn about Proxy mode when adding an A record on Cloudflare. It's important to understand how Cloudflare Proxy works and how it affects your traffic. In this module, you shouldn't enable Proxy mode, just use DNS only mode.
- Don't register a domain with a registrar that doesn't allow you to change Nameserver (NS) records. You need to have full control over the DNS settings to manage your domain properly.

## Useful Resources

- [How to set up DNS records for your domain in a Cloudflare account](https://www.namecheap.com/support/knowledgebase/article.aspx/9607/2210/how-to-set-up-dns-records-for-your-domain-in-a-cloudflare-account/): Some basic guide to point your nameserver records to Cloudflare and manage DNS records in a Cloudflare account
- [Domain Registrar or DNS Hosting](https://www.digicert.com/blog/registrar-or-dns-hosting-the-difference-explained): The basic difference between Domain registrar and DNS hosting aka why we still need Cloudflare if we purchase domain at Godaddy.com
