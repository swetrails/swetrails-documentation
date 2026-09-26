# swetrails-documentation
Public documentation for [SweTrails](https://swetrails.com), a community-edited map of hiking trails, shelters and points of interest in Sweden.

* [changes.md](changes.md) - what has changed on the site
* [TODO.md](TODO.md) - known issues and backlog
* [LICENSE](LICENSE) - MIT, covers this repository

## Direction
SweTrails is moving in three directions:
* **Organizations.** Groups can build and share their own maps on top of the shared trail data.
* **Easier crawling.** The trail data is open and simple to read in bulk.
* **Fixed licences.** Every piece of content has a clear licence, and that licence travels with the content.

## Licensing of content
| Content | Licence |
| --- | --- |
| Text: trail, POI and city resource descriptions | CC0 |
| Images | Chosen by the uploader; "All rights reserved" is not available |
| GPX tracks | Chosen by the uploader; "All rights reserved" is not available |

* "All rights reserved" cannot be chosen for new content. Older content that has it keeps its label.
* Images 750 px wide and larger carry their licence, author and a link back to the image page in the file metadata (EXIF and XMP).
* GPS position and camera details are removed from every image the site serves.

## Crawlers and API users
All crawlers are welcome on the content pages. [robots.txt](https://swetrails.com/robots.txt) lists the [sitemap](https://swetrails.com/sitemap.xml).

The public read API:
* `GET /api/poi/all` and `GET /api/route/all` list every public POI and trail.
* `POST /api/poi/batch` and `POST /api/route/batch` fetch up to 200 items by id.
* `GET /api/v1/images/{id}` serves an image, and `GET /api/v1/images/{id}/info` returns its metadata, including the licence. `{id}` is the image file name.

Every list endpoint pages the same way:
* Parameters: `page` (starts at 0), `pageSize` (1-100) and an optional `afterId`.
* Response: `{items, page, pageSize, totalPages, totalItems}`.
* An out-of-range value returns 400.
* A missing or private item returns 404.
* Timestamps are UTC.

## Where we're heading
These features are built and being tested. They are not yet switched on at swetrails.com.

**Organizations.** A group, for example a trail association, a municipality or a tourism organization, gets its own space on SweTrails:
* Owners and members, with invitations by username or email.
* Guides: curated sets of trails and POIs. In guided mode, the site suggests nearby objects, and members accept or reject them in a review queue.
* Published guides appear in search and on the Discover page.
* An organization map that can be embedded on the organization's own website, limited to domains it approves.
* A GeoJSON export of the organization's data, limited to content whose licence allows sharing.
* Organization-owned POIs and trails. An organization-owned trail can only be published if all of it is under an open licence.

**Crawler guides.** Step-by-step guides for reading routes, POIs, images, blogs and articles, the licence rules and bounding-box queries. Each request can be tried live on the page.

**Android app.** An app with offline maps is in alpha testing.
