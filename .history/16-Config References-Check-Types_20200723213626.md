# Check-Types
The type field of a CHECK controls what piece of information the comparison will be made against.

All types support the optional fields: invert

## Basic Types
All basic types support comma separated lists of values

### Module Name : **moduleName**
Checks for the presence of a module name **as listed in the part.cfg** (eg. ModuleEngines, ModuleCommand). Respects inheritance of stock classes (eg. checking for ModuleEngines will catch parts using ModuleEngines, ModuleEnginesFX, and a wide variety of Mod Engine modules)

### Part Name : **name**
Check will compare against the name field **as listed in the part.cfg** (eg. Mark1Cockpit)

### Module Title : **moduleTitle**
Checks for the presence of a module by the module name **as listed in the editor right click menu**

### Part Title : **title**
Checks for the presence of a case insensitive substring **as listed in the part title**. This is searching for partial matches so "cargo bay" will catch all stock cargo bays.

### Technology : **tech**
Matches the ID of a tech node (**NOT** the title visible ingame)

### Manufacturer : **manufacturer**
Matches the manufacturer field in the part.cfg

### Folder : **folder**
Matches to the **root** GameData folder the part is found in (eg. Squad)

### Path : **path**
Matches to the full filepath from the GameData directory to the part (eg. Squad/Parts/FuelTanks/)

### Category : **category**
Matches to the category field in the part.cfg (eg. Pods)

### Resource : **resource**
Matches to parts containing a specific resource. Matches against the ingame title (eg. Electric Charge)

### Profile : **profile**
Matches to parts with a  certain bulkhead profile listed in their part.cfg file

## Numeric Checks
Optional field valid for use with numeric types are: equality
All numeric checks support comma separated lists of values to compare against

### Crew Capacity : **crew**
Compares against the part crew capacity

### Attach Node Size : **size**
Compares against the size parameter of all the attach nodes on a part

### Mass : **mass**
Compares against the **wet** mass (the value listed when right clicking in the editor) of each part

### Cost : **cost**
Compares against the purchase price for a single part in career mode

### Crash Tolerance : **crash**
Compares against the impact speed required to destroy the part

## Other types
### Custom : **custom**
Custom type checks are shorthand for some checks that would be difficult or impossible to achieve with the standard syntax. Current valid values are: "adapter", "multicoupler", "purchased"

### Propellant : **propellant**
Checks against the resources consumed by engine modules on the part.

### Condition Group : **check**
Used to group several conditions together (eg. NOT category(Pods) AND NOT category(Engines) is different to NOT (category(Pods) AND category(Engines)). The second requires a conditional grouping to express.

### Subcategory : **subcategory**
Checks against the full conditions defined in another subcategory.