Infrastructor
=============
_Structure for your Infrastructure_

## Infrastructure Reference Name

Every entity in the Infrastructor stack has a unique identifier URI, called an Infrastructor Reference Name, or IRN. IRNs have a simple, consistent structure:

`infra:<Service>:<Partition>:<Resource>:<Identity>`

* `infra` - The URI scheme.
* `Service` - The Infrastructor service that the resource is a tenant of.
* `Partition` - The instance of the Infrastructor service that the resource is a tenant of.
* `Resource` - The resource type
* `Identity` - The service-specific identity of the resource

## Metadata Services

Track information about resources that is not directly related to their internal state, functionality, or configuration.

### [Space](doc/service/space.md)

_Track the geospatial position of everything in every dimension._ Allow resources to be grouped and queried by their physical location.

* DataCenter (Latitude/Longitude, Street Address, Building)
* Cage (Floor, Hall)
* Rack
* Elevation

#### IRNs

* `infra:space::position:<DC>/<Cage>/<Rack>/<Elevation>`

### [Asset](doc/service/asset.md)

_Track business information about resources._ When they were purchased, their depreciation schedule, maintenance services performed, etc, etc.

* Allow policies to be defined and applied to identify collections of resources missing information,
soon to be decommissioned, requiring maintenance or audit
* Provide integrations with ticketing, accounting, and purchasing systems

#### IRNs

* `infra:asset:<Partition>:facet:<Name>/<Version>`
* `infra:asset:<Partition>:resource:<ID>/<Facet>`

## Resource Services

Track physical things.

### [Box](doc/service/box.md)

#### IRNs

* `infra:resource:<Partition>:resource:<Type>/<Identity>/<>/<Port> ???`
* `infra:resource:<Partition>:component:<Type>/<Identity>/<Version>`

_Track boxes full of magic and/or clouds._ Provide a consistent representation of every piece of equipment that could ever be bolted, taped, or placed on top of something that it shouldn't be in a rack.

* Manage references to Space and Asset entities
* Provide a hierarchical model to define components and sub-components of a device.

### [Wire](doc/service/wire.md)

_Track the skinny bits that connect the boxes._ Represent a wire as an entity with an identity, a media, and two ends, each with a Spacial reference (e.g. a wire could span two racks, cages, or data centers), via the Space service, and the IRN of the component of a Box that it's connected to.

#### IRNs

* `infra:wire:<Partition>:wire:<Identity>/<End>`
