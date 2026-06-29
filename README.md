**Avian Visitors — TRMNL Plugin**

Inspired by the open source project, [Avian Visitors](https://github.com/Twarner491/AvianVisitors/tree/avian-visitors), this TRMNL plugin displays 5 recently seen birds in your area as a collage using eBird sighting data and woodblock-style bird illustrations.

**What you need to do to customize for you**

1. Create a Private Plugin in TRMNL, use the plugin settings below and add the entire markup file under `Edit Markup` 
2. Get an API key for free at ebird.org/api/keygen. Just sign in with your eBird account.
3. Update the region currently set to US-NC-119 (Mecklenburg County, NC). To change, update the regionCode (US-NC-119) in the polling URL to your target region code.
   [Find your region here](https://documenter.getpostman.com/view/664302/S1ENwy59#07c64240-6359-4688-9c4f-ff3d678a7248)
4. If you'd like to show more than 5 birds, simply adjust `MAX_BIRDS`

**How it works**

TRMNL polls the eBird API for recent bird observations in region

5 species are pulled and eaach bird is placed into a pre-computed spiral layout across the 800×480 ePaper canvas

Illustrations are fetched from the cutout API and rendered with the bird's common name below

**Plugin settings**

Strategy: Polling

Polling URL: https://api.ebird.org/v2/data/obs/US-NC-119/recent?maxResults=1000&back=7

Polling Header: x-ebirdapitoken=YOUR_EBIRD_API_KEY

No-bleed padding: Yes

**Image source**

Bird illustrations are served from bird.onethreenine.net/avian/api/cutout.php, a custom cutout API built by Teddy Warner that returns woodblock-style kachō-e illustrations keyed by scientific and common name.
