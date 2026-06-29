**Avian Visitors — TRMNL Plugin**

Inspired by the open source project, Avian Visitors, this TRMNL plugin displays 5 recently seen birds in your area as a collage using eBird sighting data and woodblock-style bird illustrations.

**What you need to do to customize for you**

1. Get an API key for free at ebird.org/api/keygen. Just sign in with your eBird account.
2. Update the region currently set to US-NC-119 (Mecklenburg County, NC). To change, update the regionCode (US-NC-119) in the polling URL to your target region code.
   [Find your region here](https://documenter.getpostman.com/view/664302/S1ENwy59#07c64240-6359-4688-9c4f-ff3d678a7248)
3. If you'd like to show more than 5 birds, simply adjust `MAX_BIRDS`

**How it works**

TRMNL polls the eBird API for recent bird observations in region
5 species are pulled and eaach bird is placed into a pre-computed spiral layout across the 800×480 ePaper canvas
Illustrations are fetched from the cutout API and rendered with the bird's common name below

**Plugin settings**

Strategy: Polling | Polling URL: https://api.ebird.org/v2/data/obs/US-NC-119/recent?maxResults=1000&back=7 | Polling Header: x-ebirdapitoken=YOUR_EBIRD_API_KEY | No-bleed padding: Yes

**Markup**

The plugin uses pure Liquid — no JavaScript — so that TRMNL's screenshot renderer captures all birds before taking the image for the device.

Bird positions are pre-computed using an Archimedean spiral algorithm with a horizontal bias (x × 1.7) to fill the landscape canvas naturally. The largest bird (most recently reported) is placed at center, with sizes stepping down from 120px to 52px as you move outward.

**Image source**

Bird illustrations are served from bird.onethreenine.net/avian/api/cutout.php, a custom cutout API built by Teddy Warner that returns woodblock-style kachō-e illustrations keyed by scientific and common name.
