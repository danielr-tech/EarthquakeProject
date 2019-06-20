## Challenge: improve your map

There are other ways your map can be modified.

+ Change the background style
+ Change the location around which the map is centred
+ Change the map projection
+ (Advanced) Add more descriptive tooltips to the plot
+ (Advanced) Turn the map into a globe

--- hints ---

--- hint ---

The background can be changed with the option `GeoBackground`.
For example, try `GeoBackground -> "ReliefMap"`.

--- /hint ---

--- hint ---

The central location can be changed with the option `GeoCenter`.

--- /hint ---

--- hint ---

The map projection can be changed with the option `GeoProjection`.
For example, try `GeoProjection -> "LambertAzimuthal"`.

--- /hint ---

--- hint ---

Tooltips can be added with `Tooltip`.
You will need to add a tooltip to each earthquake before plotting them all together.

--- /hint ---

--- hint ---

A spherical map can be made with `SphericalPlot3D`.
Here is a template:

```
SphericalPlot3D[
<any number>, (* arbitrary radius *)
{\[Theta], 0, Pi}, (* create a semicircle *)
{\[Phi], 0, 2*Pi}, (* rotate it 360 degrees to form a sphere *)
PlotStyle -> Texture[Rasterize[<your world map>]], (* add a surface texture *)
TextureCoordinateFunction -> ({#5, 1 - #4} &) (* ensure map is projected correctly *)
]
```

There are a number of options you can add to this:

+ Remove the box around the sphere with `Boxed -> False`
+ Remove the axes with `Axes -> False`
+ Stabilise the rotation with `SphericalRegion -> True`
+ Change the number of grid lines with `Mesh -> {<number of latitudinal lines>, <number of longitudinal lines>}`

--- /hint ---

--- /hints ---

![Magnitude 7+ Earthquakes around the world since 2010 (several options enabled)](images/WorldEarthquakePlotAllOptions.png)