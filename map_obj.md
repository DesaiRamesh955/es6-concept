# ES6 concept
---
## Map in JavaScript

Map is a collection of elements where each element is stored as a Key, value pair. Map object can hold both objects and primitive values as either key or value. When we iterate over the map object it returns the key, value pair in the same order as inserted

#### Syntax: 

```
new Map([it])

Parameter:
it - It is any iterable object whose values are stored as 
     key, value pair,
     If the parameter is not specified then a new map is created 
     is Empty

Returns:
A new Map object
```

Now lets create some Map using the Map object 

```js
// map1 contains
    // 1 => 2
    // 2 => 3
    // 4 -> 5
    var map1 = new Map([
        [1, 2],
        [2, 3],
        [4, 5]
    ]);
     
    console.log("Map1");
    console.log(map1);
     
    // map2 contains
    // firstname => sumit
    // lastname => ghosh
    // website => geeksforgeeks
    var map2 = new Map([
        ["firstname", "sumit"],
        ["lastname", "ghosh"],
        ["website", "geeksforgeeks"]
    ]);
     
    console.log("Map2");
    console.log(map2);
     
     
    // map3 contains
    // Whole number => [1, 2, 3, 4]
    // Decimal number => [1.1, 1.2, 1.3, 1.4]
    // Negative number => [-1, -2, -3, -4]
    var map3 = new Map([
        ["whole numbers", [1, 2, 3, 4]],
        ["Decimal numbers", [1.1, 1.2, 1.3, 1.4]],
        ["negative numbers", [-1, -2, -3, -4]]
    ]);
     
    console.log("Map3");
    console.log(map3);
     
    // map 4 contains
    // storing arrays both as key and value
    // "first name ", "Last name" => "sumit", "ghosh"
    // "friend 1", "sourav" => "friend 2", "gourav"
    var map4 = new Map([
        [
            ["first name", "last name"],
            ["sumit", "ghosh"]
        ],
        [
            ["friend 1", "friend 2"],
            ["sourav", "gourav"]
        ]
    ]);
     
    console.log("Map4");
    console.log(map4);
    ```



    
    
    