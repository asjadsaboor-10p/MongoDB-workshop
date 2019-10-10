## Exercise 8 - Geospatial queries

In this exercise we will first insert some  geo points in a collection , and then write a query to filter points that lies in a specific area.


```
    {
        name: "Parsa tower",
        location: { type: "point", coordinates: [67.0731271, 24.8635707] }
    }
```


1. Insert following location using above schema in places collection

    - Expressso Tipu sultan [24.8661546,67.0773592]
    - Habbit [24.8661546, 67.0773592]
    - Chop Chop wok [24.8661546, 67.0773592]
    - Al-Tijarah Centre [67.0749619, 24.8642376]
    - Json Trade center [67.0687145, 24.8622828]
    - Dolmen Mall Clifton [67.0276359,24.8024212]
    - Centerpoint tower [67.078582, 24.8323397]

2. Create an index on location field

3. Write a query which filters locations that are within following polygon points

    -   p1 [67.0771619, 24.8655644]
    -   p2 [67.0777401, 24.8661071]
    -   p3 [67.0784001, 24.8660038]
    -   p4 [67.0784001, 24.8660038]


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
