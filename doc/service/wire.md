Wire Service
============

_Track the skinny bits that connect the boxes._ Represent a wire as an entity with an identity, a media, and two ends, each with a Spacial reference (e.g. a wire could span two racks, cages, or data centers), via the Space service, and the IRN of the component of a Box that it's connected to.

## IRNs

* `infra:wire:<Partition>:wire:<Identity>/<End>`

## API

* `POST /wire` - Create a wire

**Request**

```json
{
  "identifier": "String",
  "media": "String",
  "ends": ["IRN<Space/Position>"]
}
```

**Response**

```json
{
  "irn": "IRN<Wire>",
  "ends": [{
    "irn": "IRN<Wire/End>",
    "position": "IRN<Space/Position>"
  }]
}
```

* `PUT /wire/IRN/END` - Connect the end of a wire to a component's port

_PUT /wire/infra:wire:default:wire:w-000000/e-000000_

**Request**

```json
{
  "port": "IRN<Box/Port>"
}
```

**Response**

```json
{
  "irn": "IRN<Wire/End>",
  "port": "IRN<Box/Port>",
  "position": "IRN<Space/Position>"
}
```
