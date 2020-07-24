# Config References: Check Types

The type field of a CHECK controls what piece of information the comparison will be made against.

All types support the optional fields: invert

## Basic Types

All basic types support comma separated lists of values

Module Name : **moduleName**

_Checks for the presence of a module name **as listed in the part.cfg** (eg. ModuleEngines, ModuleCommand). Respects inheritance of stock classes (eg. checking for ModuleEngines will catch parts using ModuleEngines, ModuleEnginesFX, and a wide variety of Mod Engine modules)_

Part Name : **name**

_Check will compare against the name field **as listed in the part.cfg** (eg. Mark1Cockpit)_

Module Title : **moduleTitle**

_Checks for the presence of a module by the module name **as listed in the editor right click menu**_

Part Title : **title**

_Checks for the presence of a case insensitive substring **as listed in the part title**. This is searching for partial matches so "cargo bay" will catch all stock cargo bays._

Technology : **tech**

_Matches the ID of a tech node (**NOT** the title visible ingame)_

Manufacturer : **manufacturer**

_Matches the manufacturer field in the part.cfg_

Folder : **folder**

_Matches to the **root** GameData folder the part is found in (eg. Squad)_

Path : **path**

Matches to the full filepath from the GameData directory to the part (eg. Squad/Parts/FuelTanks/)

Category : **category**

_Matches to the category field in the part.cfg (eg. Pods)_

Resource : **resource**

_Matches to parts containing a specific resource. Matches against the ingame title (eg. Electric Charge)_

Profile : **profile**

_Matches to parts with a  certain bulkhead profile listed in their part.cfg file_

## Numeric Checks

_Optional field valid for use with numeric types are: equality_
_All numeric checks support comma separated lists of values to compare against._

Crew Capacity : **crew**

_Compares against the part crew capacity_

Attach Node Size : **size**

_Compares against the size parameter of all the attach nodes on a part_

Mass : **mass**

_Compares against the **wet** mass (the value listed when right clicking in the editor) of each part_

Cost : **cost**

_Compares against the purchase price for a single part in career mode_

Crash Tolerance : **crash**

_Compares against the impact speed required to destroy the part_

## Other types

Custom : **custom**

_Custom type checks are shorthand for some checks that would be difficult or impossible to achieve with the standard syntax. Current valid values are: "adapter", "multicoupler", "purchased"_

Propellant : **propellant**

_Checks against the resources consumed by engine modules on the part._

Condition Group : **check**

_Used to group several conditions together (eg. NOT category(Pods) AND NOT category(Engines) is different to NOT (category(Pods) AND category(Engines)). The second requires a conditional grouping to express._

Subcategory : **subcategory**

_Checks against the full conditions defined in another subcategory._
