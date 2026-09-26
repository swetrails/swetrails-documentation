# Changes

## 2026-09-26
A summary of April to September 2026. This list covers only what is live on swetrails.com. Organizations and the crawler guides are still in development; see [README](README.md#where-were-heading).

### Licensing
* Text is CC0, as the terms of service state. Existing POI and city resource texts were moved to CC0, and the editors save new ones as CC0.
* "All rights reserved" can no longer be chosen for any content. Older content that has it keeps its label.
* The POI and city resource editors no longer show a licence picker.
* Every image shows its licence and credit, including in full-screen view and blog carousels.
* The account page has a default licence builder: three choices that give you a Creative Commons licence.
* Images 750 px wide and larger carry their licence, author and a link back to the image page in the file metadata (EXIF and XMP).
* GPS position and camera details are removed from every image the site serves.

### Crawling and the public API
Several of these are breaking changes for existing integrations.
* New catalogue endpoints `GET /api/poi/all` and `GET /api/route/all` list every public POI and trail.
* New batch endpoints `POST /api/poi/batch` and `POST /api/route/batch` fetch up to 200 items by id.
* **Breaking:** every list endpoint uses one pagination scheme: `page` (starts at 0), `pageSize` (1-100) and an optional `afterId`. It returns `{items, page, pageSize, totalPages, totalItems}`. An out-of-range value returns 400.
* A missing or private item returns 404 instead of 500.
* **Breaking:** POI `type` is now a list of keywords, for example `["ShelterWind","Firepit"]`, instead of one combined string.
* **Breaking:** routes return a `boundingBox` object instead of separate min/max fields. They now also include section colours and the municipality.
* **Breaking:** the "close by" endpoints take a `range` in metres (1-10000). The default is 500 m, which is a smaller search area than before.
* New image endpoint `GET /api/v1/images/{id}`: resized, correctly rotated and cacheable. `/info` returns its licence and details. Old image addresses redirect to it.
* The sitemap was rebuilt with `lastmod` and both languages. `robots.txt` welcomes all crawlers, AI crawlers included.
* Trail and region pages have structured data, breadcrumbs, canonical addresses and a real 404 page.

### Map and trails
* The topographic map is the default, and the layer switcher shows previews.
* City resources are shown on the map.
* Private trails and POIs: logged-in users can keep trails, including uploaded GPX, and POIs visible only to themselves.
* New Discover page, with type and difficulty filters.
* The route planner is available as a beta.
* GPX can be downloaded per section, with file names that work on Garmin devices. Uploaded GPX is cleaned and previewed.
* The map loads, pans and zooms faster.
* Region pages have an introduction, an FAQ and links to more trails in the region.
* Search was redesigned, with recent searches and provinces (landskap).

### Blog
* Users can write blogs, with tables and trail-map cards in posts.
* Every writer has a public blog page, and an overview lists all blogs.
* Posts take comments, and authors can edit and delete their own.

### Site
* New main menu, a new footer, and share buttons on trails.
* Dark mode follows the device setting.
* Image upload got tags, camera capture and clearer error messages.
* You stay logged in as long as you visit at least once a week.
* Security hardening across login and uploads.

## 2026-04-07
* new tile generator
* new markdown system using 3rd party parser
* promotion of trails
* first step on new theme management
* new main menu design
* Move image carusel to markdown
* WYSIWYG handle pasted text!
* Markdown + wysiwyg editor support grid
* auto get poi / route close to edited page for easy linking

## 2023-07-23
* Custom markdown pages
* Improved mobile support. Now users can minimize current page to the left/bottom of the screen to see the map
* New routing url scheme to support subpages for trails in the future
* Fixed mobile scaling issue being bad for mobile user experence, by google
* Fixed wrong link type not beeing detectable by google
* Fixed bad image manaagment in the WYSIWYG
* Fixed WYSIWYG not working until at least 2 lines been written in it

## 2023-05-19
* Removed users ability to chagne url, after the poin been created
* Fixed menu element that did not close on externalEvents
* Map editing tools are no longer auto selected
* Reworked layout of segment editing tools, improved layout and informational text.

## 2023-05-18
* Added text for when no edit have been made on a page
* If user not logged in uploads a image. A message has been added for login/create account

## 2023-05-16
* Anonymous users can now only upload images udner CC0. Added message for user to login to upload under other license
* Changed text licens to CC0
