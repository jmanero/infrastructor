Wire Service
============

_Track the skinny bits that connect the boxes._ Represent a wire as an entity with an identity, a media, and two ends, each with a Spacial reference (e.g. a wire could span two racks, cages, or data centers), via the Space service, and the IRN of the component of a Box that it's connected to.

## IRNs

* `infra:wire:<Partition>:wire:<Identity>/<End>`

## API

* `POST /wire` - Create a wire

* `PUT /wire/IRN/END` - Connect the end of a wire to a component's port
