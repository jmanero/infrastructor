Space Service
=============

_Track the geospatial position of everything in every dimension._ Allow resources to be grouped and queried by their physical location.

* DataCenter (Latitude/Longitude, Street Address, Building)
* Cage (Floor, Hall)
* Rack
* Elevation

## IRNs

* `infra:space::position:<DC>/<Cage>/<Rack>/<Elevation>`

## API

* `POST /dc` - Create a DataCenter

```json
{
  "latitude": "Number",
  "longitude": "Number",
  "address": "String",
  "building": "String"
}
```

* `POST /dc/IRN/cage` - Add a Cage to a DataCenter

_POST /resource/infra:space::position:dc-000000/cage_

```json
{
  "floor": "String",
  "hall": "String"
}
```

* `POST /cage/IRN/rack` - Add a Rack to a Cage

_POST /resource/infra:space::position:dc-000000/cage-000000/rack_

```json
{
  "x": "String",
  "y": "String",
  "height": "Number",
  "depth": "Number"
}
```

* `POST /rack/IRN/resource` - Add a Resource to a Rack

_POST /resource/infra:space::position:dc-000000/cage-000000/rack-000000/resource_

```json
{
  "elevation": "Number",
  "mounting": "String[FRONT|REAR|INTERNAL]",
  "height": "Number",
  "depth": "Number",
  "irn": "IRN"
}
```
