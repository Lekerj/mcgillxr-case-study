# 6. The menu flickered on 3G

[← Previous](05-posters-broke-the-grid.md) · [Home](../README.md) · [Next →](07-moving-the-domain.md)

## The problem

On a phone with a slow connection, tapping a link in the menu did three things wrong:

1. the menu flashed open for a few frames
2. the page flashed white, on a site with a black background
3. the header appeared without the logo

## The root cause

They looked like three separate bugs, but they had one cause. What the browser drew first
depended on the stylesheet, and on a slow connection the stylesheet hadn't arrived yet.

- The page background was set in the stylesheet, so until it loaded the browser used its
  default white.
- The menu's HTML started in the open state, and only the script closed it.
- The logo was drawn with a CSS mask, so the browser didn't know the image existed until it
  had read the stylesheet.

## The fix

- I put the few rules the first frame needs (the page background and the closed menu)
  directly at the top of the page, before anything else.
- The menu now starts closed in the HTML.
- The logo is a regular image, which the browser finds in the first bytes of the page. I
  also resized it from 1200 px to 600 px (57 KB to 24 KB), since it never shows wider than
  160 px.
- Tapping a link closes the menu, so going back doesn't show the page with the menu open.

## Testing it

I recorded the page frame by frame on emulated slow 3G, fast 3G and slow 4G, with the CPU
slowed down four to six times. None of the three problems showed up, and the light theme
and desktop view were unaffected.

## The result

Lighthouse on the live site (October 16, 2026):

| Page | Performance (desktop / mobile) | Accessibility | SEO |
| --- | :-: | :-: | :-: |
| Home | 99 / 91 | 100 | 100 |
| Events | 99 / 95 | 100 | 100 |
| Sponsors | 99 / 98 | 100 | 100 |

Layout shift is zero on all three pages. The home page scores lowest on mobile because of
its background video.
