Group by is a very small Nim dependency with implements `groupBy` and `keyVal` `func`'s.

# Usage
```nim
import groupby
import sugar
import tables
type 
  BreadType = enum
    Wheat = "Wheat", Rye = "Rye"
  Topping = enum
    OliveOil = "OliveOil", Mammi = "Mämmi"
  

let foods : seq[(Breadtype, Topping)] = @[(Wheat, OliveOil), (Wheat, OliveOil), (Rye, Mammi), (Rye, OliveOil)]

let grouped = foods.groupBy(x=> x[0], x=> x[1])

# {"Rye": @[Mämmi, OliveOil], "Wheat": @[OliveOil, OliveOil]}
echo grouped


let keyvald = foods.keyval(x=> x[0], x=> x[1])

# {"Rye": OliveOil, "Wheat": OliveOil}
echo keyvald
```
