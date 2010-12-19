# Map Charts Tiles

This is a sunday experiment hacking with the new Google Map Charts API (http://code.google.com/apis/chart/docs/gallery/new_map_charts.html) and Google Maps V3 (http://code.google.com/apis/maps/documentation/javascript/).

Check out [this example of the Number of World Heritage properties inscribed by each Country](http://vizzuality.s3.amazonaws.com/gmapcharts/whs_by_country.html )

The introduction of the new Map Charts API allow to use the API as a Tile generator for Google Maps V3. That makes it a very powerful tool for thematic mapping on Google Maps V3. For example, traditionally it has been very difficult to highlight one country with precission in Google Maps. Most people used polygons to do so but did not work well because of performance. Using this technique this is a very easy and performing way of doing it.

## How does it work technically?

The new Map Charts API allows you to define the viewport of the map you are generating in lat/lon. For example here you have a map of the whole world: 

![Tile 0,0,0](http://chart.apis.google.com/chart?cht=map:fixed=-85,-180,85,180&chs=256x256&chld=HT&chco=B3BCC0|FF0000|000000&chf=bg,s,FFFFFF
)

The idea is to use the API as a ImageMapType in Google Maps v3 (or a TileLayerOverlay in Google Maps For Flash). To do so in the the getTileUrl we need to do a transformation from Tile X/Y/Z coordinates to Lat/Lon coordinates. This is an easy operation, with some math. Actually it looks very similar to an OGC Web Map Service. In some sense, I would say that Map Charts API is the first "kind of" WMS server that performs well (jatorre, 2010 :D ).

## Does it only work on Google Maps?

No!! You can use this technique in almost all mapping libraries out there. Essentially anything that supports overlaying tiles in 900913 projection (often call Google Projection, Web mercator,etc.). So from what I can say this could be used in:

* Google Maps V2 and V3
* [OpenLayers](http://openlayers.org/)
* [Google Maps For Flash](http://code.google.com/apis/maps/documentation/flash/)
* [Bing Maps](http://www.microsoft.com/maps/developers/web.aspx)
* [Yahoo Maps](http://developer.yahoo.com/maps/)
* [OpenScales](http://openscales.org/)

If you want to have some examples on a specific platform let me know and I will try to provide them.

## What kind of maps can be generated like this?

To be done.. checkout the examples for the moment.

## What are the supported regions for mapping?

The description on the Maps Chart API is quite small (http://code.google.com/apis/chart/docs/gallery/new_map_charts.html#supported_params). It says: "These codes are ISO 3166-1-alpha-2 codes: two uppercase characters, optionally followed by a dash and a second identifier for regions or cities. Examples: GB (Great Britain), GB-LND (London), US-NJ (state of New Jersey in the United States)"

The country codes can be found on Wikipedia: http://en.wikipedia.org/wiki/ISO_3166-2 But the region codes within a country are a bit more complicate. Google seems to be using "statoids", but not always, you will have to try. For a list of statoids check out http://www.statoids.com/.

## Future

I am for the time being just having fun with the technique, but I am not even sure if this is a fair use of the Map Charts API. I have asked in Twitter and the Google Maps V3 forum but still havent received any answer.

If this is ok with Google there is a lot of things that can be done. A full thematic mapping library can be done using this technique. Also lot of interesting stuff to highlight countries and regions when using Google Maps, or for displaying clusters,icons or even graphs on maps...

## Participate

Send me an email [jatorre@vizzuality.com](mailto:jatorre@vizzuality.com) in case you feel like contributing.

Javier
[www.vizzuality.com](http://www.vizzuality.com)
