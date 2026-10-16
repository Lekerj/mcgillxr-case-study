# 7. Moving the domain

[← Previous](06-the-menu-flickered-on-3g.md) · [Home](../README.md) · [Next →](08-photos-of-real-people.md)

## The problem

Once the site was on its temporary address, links shared on Instagram, Discord, Slack and
Snapchat showed a grey box instead of a preview image. Every page told those apps to fetch
its preview from `mcgillxr.ca`, which didn't work yet.

## A safe stopgap

I pointed the site's address setting at the temporary address so previews worked in the
meantime. Then I set one rule for the switch: before changing the setting back, open the
preview image at `mcgillxr.ca` in a browser, and only continue if it loads.

## Making the switch

The domain didn't need to be transferred to another company. The registrar (where it's
renewed) and the nameservers (where it points) are separate, so only the nameservers had to
change. The order was:

1. unlock the domain at the registrar
2. add it to Cloudflare and delete the old `www` record pointing at Google
3. replace Google's nameservers with Cloudflare's
4. once Cloudflare showed it as active, attach the domain to the site
5. check that the preview image loads at `mcgillxr.ca`
6. change the site's address setting, which updates every link, preview and search listing

Any step could be undone by putting the old `www` record back.

## The result

`mcgillxr.ca` went live on October 16, 2026. `www.mcgillxr.ca` serves the same pages and
tells search engines that `mcgillxr.ca` is the address to index. The temporary address is
now turned off, while test versions of other branches still get their own preview links.
I didn't touch the old Google Site at any point.
