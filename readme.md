## js-module-nearestPlace

This module helps you find neearest place from your lists.
real deal example: find nearest outlets from current location


you might need coordinate(long, lat), and lists of your places to compare (long, lat) 


version 1.0.0

--------

### get(loc, objList, callback)
This will find the nearest place from your location

params
```
param: loc
desc: current coordinate
type: array
required: true
format: [long, lat]
example: [
    long: 12.002,
    lat: -9.23
]
```
```
param: objList
desc: lists places you want to get the nearest from 
type: array
required: true
format: [ [long, lat], [long, lat], ....]
example: [
    [
        long: 2.102,
        lat: -93.23
    ],
    [
        long: 2.002,
        lat: -19.23
    ],
]
```
```
param: callback
desc: callback action to be called after this module got the nearest object (to get result)
type: object
required: true
format: rslt => {}
example: rslt => {
    console.log(rslt)
}

```


docs
```
import nearestPlace from 'js-module-nearestPlace'



const loc = {
    long: "1.002",
    lat: "23.12"
}

const outlets = {
    {
        name: "outlet1",
        long: "1.002",
        lat: "23.12"
    },
    {
        name: "outlet2",
        long: "1.002",
        lat: "23.12"
    },    
}

nearestPlace.get(loc, outlets, (rslt) => {
    console.log('result',rslt)
    if (rslt < 0) {
        // no service
    } else {
        // returning nearest (nearest value found on outlets - index value)
        console.log (rslt)
        console.log (outlets[rslt])
    }
})
```
