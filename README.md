# guvtmap
Public facing map for Green Up data viewing

## Intro
The basic premise is that some places will want to be able to show a map of Green Up status.

It might be for a news website. It might be the Green Up website.

It might also be used as an operational display for town organizers in a town's Green Up HQ. This is what happens in Montpelier where they setup a table at the farmer's market and have a big display of which streets are claimed and being cleaned, etc. So in that case they need to show it full-screen.

## Params
Ideally this needs a toolbar to toggle some values. Presently it is controlled through URL params.

* *trashDrops*=[true||false] - show trash bags filled and logged in the app... scaling the display on the map by the number of bags collected for that logged entry.
* *onlyTrashMarkers*=[true||false] - if trash bags filled are shown, do not scale their display by the number of bags collected.
* *teamAreas*=[true||false] - show the locations claimed by the various teams ... where are people greening-up?
* *supplySites*=[true||false] - show where you can pickup the Green Up Vermont bags
* *collectionSites*=[true||false] - show where you should bring your filled bags if you cannot leave them by the side of the road for your road crew to pickup (depends on the town)
* *town*=MONTPELIER - start the map zoomed to, and highlighting, a particular town... graying out all others
* *hideToolbar*=[true||false] - when we eventually have a toolbar to control all this, make it possible to hide via this param

## What We Still Need
We still need some functionality to make this work well for the public.
* We need a toolbar at the top or bottom that can control the params outlined above (if not others I haven't thought of)
* We need to test how well it works for the color blind
* We need to add a refresh that can _either_ watch the firebase for updates and update the map as they happen (the harder way), _or_ it does an HTML page refresh with the META tag (if I recall) every X minutes automatically (the simpler / old-school way)... maybe toggle-able on/off. So if Montpelier is using this full screen all day, it should keep refreshing the display one way or another.
* Code for BTV Logo and attribution and link to our website
* We need a legend to tell people what the heck the map symbols represent
* The town name, when entered, currently must be ALL UPPERCASE because that is how the town name attribute is storing it in the GeoJSON. We should probably make it smart enough to accept different cases of town names.