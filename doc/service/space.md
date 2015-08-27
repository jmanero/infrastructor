Space Service
=============

_Track the geospatial position of everything in every dimension._ Allow resources to be grouped and queried by their physical location.

* DataCenter (Latitude/Longitude, Street Address, Building)
* Cage (Floor, Hall)
* Rack
* Elevation

## API

* `POST /dc` - Create a DataCenter

```json
{
  "latitude": "Number",
  "longitude": "Number",
  "address": "String",
  "building": "String",
  "identity": "String"
}
```

* `POST /dc/URN/cage` - Add a Cage to a DataCenter

```json
{
  "floor": "String",
  "hall": "String",
  "identity": "String"
}
```

* `POST /cage/URN/rack` - Add a Rack to a Cage

```json
{
  "x": "String",
  "y": "String",
  "identity": "String",
  "height": "Number",
  "depth": "Number"
}
```

* `POST /rack/URN/resource` - Add a Resource to a Rack

```json
{
  "elevation": "Number",
  "mounting": "String[FRONT|REAR|INTERNAL]",
  "height": "Number",
  "depth": "Number",
  "urn": "URN"
}
```
