Box Service
===========

_Track boxes full of magic and/or clouds._ Provide a consistent representation of every piece of equipment that could ever be bolted, taped, or placed on top of something that it shouldn't be in a rack.

* Manage references to Space and Asset entities
* Provide a hierarchical model to define components and sub-components of a device.

## IRNs

* `infra:resource:<Partition>:resource:<Name>/<Version>`

## API

* `POST /resource` - Create a resource

* `POST /resource/IRN/conponent` - Add a component to a resource

* `POST /component` - Define a component
