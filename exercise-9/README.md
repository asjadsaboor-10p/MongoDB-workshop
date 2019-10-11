## Exercise 9 - Geospatial queries

In this exercise we will first insert some  geo points in a collection , and then write a query to filter points that lies in a specific area.


```
    {
        name: "Parsa tower",
        location: { type: "point", coordinates: [67.0731271, 24.8635707] }
    }
```


1. Insert following location using above schema in places collection

    - Expressso Tipu sultan [ 67.0773592, 24.8661546 ]
    - Habbit [ 67.0773592, 24.8661546 ]
    - Chop Chop wok [ 67.0772784948349,24.865777329446257 ]
    - Al-Tijarah Centre [ 67.0749619, 24.8642376 ]
    - Json Trade center [ 67.0687145, 24.8622828 ]
    - Dolmen Mall Clifton [ 67.0276359,24.8024212 ]
    - Centerpoint tower [ 67.078582, 24.8323397 ]

2. Create an index on location field

3. Write a query which filters locations that are within following polygon points

     -  p1 [ 67.0769190788269, 24.86639058396931 ]
     -  p2 [ 67.07674741744995, 24.865699455638346 ]
     -  p3 [ 67.07710146903992, 24.864988854875172 ]
     -  p4 [ 67.0785927772522, 24.865446365423864 ]
     -  p5 [ 67.078195810318, 24.86678968448509 ]
     -  p6 [ 67.0769190788269, 24.86639058396931 ]

4. Write a query to insert above polygon in `areas` collection.

5. Write a query to find which of the following points lies in above area.

    - p1  [ 67.07785785198212, 24.865908741385855 ] 
    - p2  [ 67.0813125371933, 24.861445524359674 ]


Hints:

Here's how you can give polygon cordinates

```
{
  type: "Polygon",
  coordinates: [ [ [ 0 , 0 ] , [ 3 , 6 ] , [ 6 , 1 ] , [ 0 , 0  ] ] ]
}

```

Geospatial Query Operators

   -   $near
   -   $geoWithin
   -   $geoIntersects
