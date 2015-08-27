Asset Service
=============

_Track business information about resources._ When they were purchased, their depreciation schedule, maintenance services performed, etc, etc.

* Allow policies to be defined and applied to identify collections of resources missing information,
soon to be decommissioned, requiring maintenance or audit
* Provide integrations with ticketing, accounting, and purchasing systems
* Provide a queryable store for any technical information about a resource that isn't necessary for its programatic allocation (e.g. A RAM DIMM's manufacturer, or the batch number of a hard disk)

The underlying data model of an Asset is loosely structured into Facets, which contain structured data collections specific to some business function and drive integrations with external services.

* Facets are defined dynamically via the API with a set of typed fields a friendly name, and a version.
* Facets are identified and referenced by IRNs including their names and versions.

## IRNs

* `infra:asset:<Partition>:facet:<Name>/<Version>`
* `infra:asset:<Partition>:resource:<ID>/<Facet>`

## API

* `POST /resource` - Add a resource

```json
{
  "irn": "IRN",
  "facets": [
    {
      "irn": "IRN"
      "attributes": {
        "..."
      }
    }
  ]
}
```

* `POST /resource/IRN/facet` - Add a facet to a resource

_POST /resource/infra:asset:default:resource:r-000000/facet_

```json
{
  "name": "String",
  "attributes": {
    "..."
  }
}
```

* `POST /facet` - Define a facet

```json
{
  "name": "String",
  "version": "Semver",
  "require": "Boolean",
  "multiple": "Boolean",
  "attributes": {
    "<NAME>": {
      "type": "Type",
      "require": "Boolean",
      "default": "Value<Type>"
    }
  }
}
```
