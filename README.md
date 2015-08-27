Infrastructor
=============
_Structure for your Infrastructure_

## Metadata Services

Track information about resources that is not directly related to their internal state, functionality, or configuration.

### [Space](doc/service/space.md)

_Track the geospatial position of everything in every dimension._ Allow resources to be grouped and queried by their physical location.

* DataCenter (Latitude/Longitude, Street Address, Building)
* Cage (Floor, Hall)
* Rack
* Elevation

### [Asset](doc/service/asset.md)

_Track business information about resources._ When they were purchased, their depreciation schedule, maintenance services performed, etc, etc.

* Allow policies to be defined and applied to identify collections of resources missing information,
soon to be decommissioned, requiring maintenance or audit
* Provide integrations with ticketing, accounting, and purchasing systems

## Resource Services

Track physical things.

### [Box](doc/service/box.md)

_Track boxes full of magic and/or clouds._ Provide a consistent representation of every piece of equipment that could ever be bolted, taped, or placed on top of something that it shouldn't be in a rack.

* Manage references to Space and Asset entities
* Provide a hierarchical model to define components and sub-components of a device.

### [Wire](doc/service/wire.md)

_Track the skinny bits that connect the boxes._ Represent a wire as an entity with an identity, a media, and two ends, each with a Spacial reference (e.g. a wire could span two racks, cages, or data centers), via the Space service, and the URN of the component of a Box that it's connected to.
