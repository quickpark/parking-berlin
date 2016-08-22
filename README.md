# Berlin Parking Probabilities

This dataset contains information about the per-street probabilities of finding a parking spot for different roads in the city of Berlin, Germany.

The database has been collected by [TomTom Germany](https://www.tomtom.com/) and was used for the experimental evaluation in *[Probabilistic routing for on-street parking search](http://drops.dagstuhl.de/opus/volltexte/2016/6348/pdf/LIPIcs-ESA-2016-6.pdf) by Arndt et Al. (2016)*. You can read about the data collection method in *section 5* of the linked research paper.

To facilitate a full release of the parking information, the data has been transferred from the proprietary format of TomTom to the open-source [OpenStreetMap](https://www.openstreetmap.org/) road network. All segments are matched to the OSM road geometries, based on the [Geofabrik OSM release](http://download.geofabrik.de/europe/germany/berlin.html).
## Structure

The file `probabilities.osm` contains information about the parking probabilities in the city of Berlin. The structure is (loosely) based on the [OpenStreetMap XML format](https://wiki.openstreetmap.org/wiki/OSM_XML). You can learn more about the OSM XML elements [here](https://wiki.openstreetmap.org/wiki/Elements).

All original OSM `<way>` elements have been split up into their segments to allow for a higher resolution of per-way attributes. Therefore, in this release a `<way>` element defines a segment between exactly two points with tags giving details about its parking properties. The `parking` tag denotes the *density* which is the parking probability for a unit-length part of the road. The terminology as well as the translation between *probability* and *probability density* values is described in the research paper in *section 5*. The value of each `parking` tag is a comma-separated list of 7 * 24 density values, each for one hour in the week, starting from Monday, 0:00.


## License

```
MIT License

Copyright (c) 2016

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

```
