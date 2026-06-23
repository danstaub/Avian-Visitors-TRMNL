Avian Visitors — TRMNL Plugin

A TRMNL OG private plugin that displays a spiral collage of recently spotted birds in Mecklenburg County, NC using eBird sighting data and woodblock-style bird illustrations.

How it works


TRMNL polls the eBird API for recent bird observations in Mecklenburg County
Up to 12 species are pulled, sorted by most recently reported
Each bird is placed into a pre-computed spiral layout across the 800×480 ePaper canvas
Illustrations are fetched from the cutout API and rendered with the bird's common name below


Setup

Plugin settings

FieldValueStrategyPollingPolling URLhttps://api.ebird.org/v2/data/obs/US-NC-119/recent?maxResults=12&back=7Polling Headerx-ebirdapitoken=YOUR_EBIRD_API_KEYNo-bleed paddingYes

Getting an eBird API key

Free at ebird.org/api/keygen. Just sign in with your eBird account.

Markup

The plugin uses pure Liquid — no JavaScript — so that TRMNL's screenshot renderer captures all birds before taking the image for the device.

Bird positions are pre-computed using an Archimedean spiral algorithm with a horizontal bias (x × 1.7) to fill the landscape canvas naturally. The largest bird (most recently reported) is placed at center, with sizes stepping down from 120px to 52px as you move outward.

Image source

Bird illustrations are served from bird.onethreenine.net/avian/api/cutout.php, a custom cutout API built by Teddy Warner that returns woodblock-style kachō-e illustrations keyed by scientific and common name.


Perched: ?sci={sciName}&com={comName}
In flight: ?sci={sciName}&com={comName}&pose=2


Region

Currently set to US-NC-119 (Mecklenburg County, NC). To change region, update the regionCode in the polling URL to any valid eBird region code.

Layout

ParameterValueCanvas800 × 480 pxCollage area800 × 450 px (below 30px title bar)Max birds12Largest bird120pxSmallest bird52pxSpiral biasHorizontal (x × 1.7)
