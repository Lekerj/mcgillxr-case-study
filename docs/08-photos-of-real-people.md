# 8. Photos of real people

[← Previous](07-moving-the-domain.md) · [Home](../README.md)

## The problem

A public club website is full of students' faces, and some of those photos raised questions
that had nothing to do with code.

## Hidden data in photos

Eight published images still had camera and editing data embedded in them. None had GPS
data, but I checked rather than assumed. I removed only that data and left the images
themselves untouched. The originals, data included, are kept outside the repo.

## Giving credit

Nobody had kept track of who took which photo. I went through the club's shared drive, read
only, and matched each photographer's camera series to the event folders. Event pages now
show "Photo:" with a name under those photos, and the About page lists every credit. Where
nothing pointed to a photographer, I left the photo uncredited instead of guessing. Some
credits are still waiting on the photographer to confirm, and they're listed in the to-do
list. Posters already carry their own credits, so I left them alone.

## Consent

One past event, a family day at a hospital, had photos that all showed children, with no
record of parental consent and no poster to use instead. I took the event off the site. It's
still in version history and can come back if a photo with consent turns up.

## Quebec privacy law

Quebec's Law 25 requires a named person responsible for personal information. The privacy
page names the club's President, by role so it stays valid when the team changes, with a
reply within 30 days. It also says that anyone who doesn't want to appear in event photos can
tell the team, or email afterwards, and the photo will be removed.
