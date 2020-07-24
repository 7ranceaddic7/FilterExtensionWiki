Finding all engines that consume a mix of Liquid Oxygen and Liquid Hydrogen only

**Conditions**
* Must show all engines that:
  * Consume LH and LOx
  * Do not consume any other resources

```
FILTER
{
    CHECK
    {
        type = propellant
        value = LiquidHydrogen
    }
    CHECK
    {
        type = propellant
        value = LiquidOxygen
    }
}
```
There are several traps to watch for here. First, because both propellants are required they must be listed in conditions. The second is that this is incomplete, an engine using a third or fourth resource would still be capable of matching these conditions.

```
FILTER
{
    CHECK
    {
        type = propellant
        value = LiquidHydrogen
    }
    CHECK
    {
        type = propellant
        value = LiquidOxygen
    }
    CHECK
    {
        type = propellant
        value = LiquidHydrogen, LiquidOxygen
        invert = true
        contains = false
    }
}
```
This third check is using two optional parameters, invert and contains. "contains = false" means "is there a propellant NOT on this list in this engine". It will only return true if there is a third propellant type. But it should only return true when there is NOT a third propellant, so we invert the result with the line "invert = true"

You may have noticed the lack of a specific check for an engine. Propellant nodes return false when no engine is found so in this case we can skip that.