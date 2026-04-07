# Frontend

## High
* Unable to update route from mobile phones 
* Orientation on currently uploading images in image rotate thing.
* Upload private gpx tracks (only visible for the user)
* Blog support (Custom markdown pages)
* Page support (partially implemented but not fully, for tutorials on hiking and such)
* AI assistant to help with spellchecking and grammar in markdown and wysiwyg, auto injection of links

## Backlog
* New POI - Culture
* Upload private images(licens and still public but unbound)
* fix route bounds weast/east/... so that it can include over the world border of 180
* Documentation on what section number is in editLinePage

# Combined
* Fileuploader naming can fail if provided filename is not equal to provided file. (Dump filename from form content)
* Page lock (Lock pages from change (Privalage management?)

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -  

# Backend

## High
* Fix the email server to work with the new email system (currently not working)
* jpeg endings can be converted to jpg. and then they don't match.
* Send email when new images has been added for verification

## Backlog
* APi usage statistics
* API statistics as timers, packageSize, request count
* Data transfer statistics
* Privalage(permission) management on url_id


## Springboot - Web crawler / repeat batch work every x hour/day/month
* [24Hour]	verify that routes/pois has text for all available url languages (delete url language if not is the case when age>24H)
* [7Day]	Clear all files that has no links
* [7Day]	verify all links in database. Even in markdown
* [1Month]	(Auto generation checker needs to be built) check page for changes EX: DANO https://dalslandnordmarken.se/sv/lagerplatser/

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

# General
* System to follow "right to erasure" (Deletion of any information that can be used to identify a person [Data may be saved for legal reasons]) [MANUALY DONE CURRENTLY]