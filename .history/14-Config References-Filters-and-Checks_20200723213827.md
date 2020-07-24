FILTER and CHECK nodes are the basis for setting which parts are visible in each Category and Subcategory.

### FILTER nodes contain a set of conditions
Each category and subcategory can have multiple filters available, with a part being required to meet all the conditions of atleast one filter to be visible. Filters can also be inverted so the reverse is true (must not pass any nodes to be visible) but this is generally not required

### CHECK nodes contain the details of a single condition
Each check node contains a single yes/no condition that a part must pass to be accepted. Each Check has a type which details what on the part will be compared against as well as a value (or list of values) and several optional parameters.
```
// an example Filter checking for all parts that would be visible in the stock "Pods" subcategory
FILTER
{
    CHECK
    {
        type = category
        value = Pods
    }
}
```
All valid Check types are listed [HERE](https://github.com/Crzyrndm/FilterExtension/wiki/Check-Types)