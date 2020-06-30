# unitdb
A simple JSON database containing conversion factors and other information for 
a large number of measurement units

## Repository Structure

* The db.json file contains all prefix and unit definitions
* The schema.json file is a jsonschema that defines the structure of the 
  db.json file
* The nist811 folder contains .csv that contain conversion factors defined by 
  NIST [more info](./nist811/TableInfo.md)

## db.json
This file contains definitions for standard (SI) prefixes and measurement units 
(SI and non-SI). Each field is keyed by it's most common symbol. Prefixes are 
structured as in the following example:

```json
{
    "m": {
        "scale": "1e-3",
        "name": "milli"
    }
}
```

This tells us that the prefix "m" modifies a value by a multiple of 1e-3 and it's
full name is "milli".

Units are defined as in the following example:

```json
{
    "gf": {
        "name": "Gram Force",
        "description": "Defined as the amount of force exerted by standard gravity on a 1 gram mass",
        "category": "force",
        "scale": "9.80665e-3",
        "dimensions": {"mass": 1, "length": 1, "time": -2},
        "aliases": ["pond"]
    },
}
```

This tells us that the "gf" symbol is defined a Gram-Force, it has dimensionality
(mass * length / time^2), and has a scale of 9.80665e-3 relative to the SI
standard measure of force (the Newton). Common alternative symbols are in the
aliases array. Note that scale values are implemented as strings rather than floating
point literals because some units can be precisely defined with a mathematical
expression. For example, the US Survey Foot is defined as `1200/3937` meters and a 
Revolution is defined as `2*pi` radians, both of which cannot be represented 
exactly in floating point.
