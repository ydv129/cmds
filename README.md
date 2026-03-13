# Practical 1: Creating and Managing Vector Data: Adding vector layers, setting properties, formatting, calculating line lengths and statistics

## Part 1
```
1. Layer-create layer - new shape file layer - select point - Add name - click add attribute to list - OK
2. Give your File name-Save
3. On left side-select to Toggle Editing-Select Add features - click anywhere in the screen-Give ID - Click OK
4. For Line and Polygon repeat the steps and select line and polygon in step 1
```

## Part 2
```
1. Layer → Add Layer → Add Vector Layer
2. From Practical 1(D) folder open → "IND_adm0.shp"
3. Layer → Add Layer → Add Vector Layer
4. From Practical 1(D) folder open → "IND_rails.shp"
5. From Layers in the left → Right click on the "IND_rails" → Click on Open Attribute Table
6. Click on Toggle editing mode (editing mode will be on)
7. Click on Open Field Calculator → Give the output Field name as "Track_len2" and change output field type to Decimal number
8. Then write the formula $length/1000 click on OK
9. Vector → Analysis Tools → Basic Statistics
10. In the Input vector layer → select IND_rails
11. In the Target field → select Track_len2 and Run and Close and values will be seen
```

# Practical 3: Exploring and Managing Raster data: Adding raster layers, raster styling and analysis, raster mosaicking and clipping.

## Part 1:
```
1. Layer → Add Layer → Add Raster Layer From Practical 2(A) folder open → "glds90g60.asc"
2. From Layers in the left → Right click on the "glds90g60" → Click on Properties
3. In Properties Change Render type to "Singleband pseudocolor" Change Mode to "Equal Interval" Change the color Then click on "classify" and then ok
4. Repeat step 1 and select the file "glds00g60.asc" and open
5. In the properties of "glds00g60" Change the Render type Set the Max value to 240 Change the Mode Click on classify and then apply and ok
6. From Layers select both the file by clicking on the box
7. Click on Raster → Then click on "Raster Calculator"
8. In Raster Calculator From the Raster Bands → Select "glds00g60@1" (By double clicking on it) From the operators, select the "-" operator Then the "glds90g60@1" from the Raster Bands In the Result Layer, Click on the 3 dots of the output layer Create a file named "Diff" in the "Practical 2 folder → Click on the "Save" and ok
9. Then from the layers go to the properties of "Diff" file
10. Repeat step 5, click on classify and ok
```

## Part 2
```
1. Layer → Add Layer → Add Raster Layer From Practical 2(C) folder → open "India" folder, select the "4 images"
2. Raster → Miscellaneous → Merge
3. In the output file → Create a file named "merged" in the "Practical 2" folder and "Save"
4. In the input files → Select all the "4 images" which were selected previously from the "India" folder
5. Layer → Add Layer → Add Vector Layer From "IND_adm0.shp" file and open
6. Raster → Extraction → Clipper In the Input file → Select the "merged" file created previously In the output file → Create a file named "Clip" and Save Change the clipping mode to "Mask Layer" and ok and then close
```

# Practical 4: Making a Map, Working with Attributes, Importing Spreadsheets or CSV files Using Plugins, Searching and Downloading OpenStreetMap Data

## Part 1: India Map
```
1.Layer- add vector-select image (adm0_shp)
2. Project-new print composer-give name
3.New interface is opened
4.Layout-add map-select and drag
5.layout-add image-select and drag-go to item-search directories-select image
6.layout-add image-select and drag-go to item-search directories-select image
7.layout-add label-select and drag-go to item-search directories-write any text
8.layout-add scale bar- select and drag
9.layout-add arrow- select and drag
10.layout-add legend - select and drag
11.layout-add attribute /table - select and drag
12.Left side select shapes and select and drag-go to item-search directories-change color
13.Composer-Export as Image-Give Name -save
```

## Part 2- Mumbai Map
```
1. Layer-add- Raster-Select Image-(mumbai-map.jpg)
2. Project-new print composer-give name
3. New interface is opened
4. Layout-add map-select and drag
5. Layout-add image-select and drag-go to item-search directories-select image
6. Layout-add image-select and drag-go to item-search directories-select image
7. Layout-add label-select and drag-go to item-search directories-write any text
8. Layout-add scale bar - select and drag
9. Layout-add arrow- select and drag
10. Layout-add legend - select and drag
11. Layout-add attribute /table - select and drag
12. Left side select shapes and select and drag-go to item-search directories-change color
13. Composer-Export as Image-Give Name -save
```

## Part 3: Sample File
```
1. Select layer-Add layer-Add delimited text layer
2. File Name-Select sample.xls
3. Select custom delimiters-Select all the checkboxes
4. In geometry definition -x field - (select LATITUDE) -y field- (select LONGITUDE)
5. Click OK - Close - Cancel
```

# Practical 5: Working with attributes, terrain Data

## Part 1:
```
1. Open New Project
2. Click on Layer → New Layer → Add Vector Layer
3. Browse "Practical 4" dataset → Select the zip file “ne_10m_populated_places_simple” and click "open"
4. Right click on that file → Click on "open attribute table"
5. From above tools → Click on "Select feature using an expression"
6. Put this formula in textbox pop_max > 10000 and sov0name = 'India'
7. Click on select and close.
```

## Part 2:
```
1.Layer- Add layer - Add raster layer - select image with end (mea300.tif extension file)- .tif layer is displayed on screen
2. Select raster-Extraction-Select Clipper
3.Check input file whether that is the same filename as you selected prior
4.In output file-select-give any name to your file-Save
5.Drag and Select the displayed image and click OK-OK-OK and close
6.On the left side untick the filename mea300.tif which you have selected prior then your clipped layer will be displayed.
7.Select raster-Extraction-Select Contour
8.Check input file and drop and select the clipped file
9.In output file-Select-give any name to your file-Save
10.Change interval between contour line into 100 and check the Attribute name-Elev
11.Click OK-OK-OK and close
12.Right click on the contour file from the layers section on the left bottom side
13.Open Attribute table and new window will be displayed - click ELEV and select downward triangle to get highest value
14.Select first row then select the Zoom map to the selected row icon and close that window you will get the output
15. Again, repeat step 12
16.Right on the contour file and go to properties-select label-select checkbox in label this layer and select ELEV from dropdown
17.Click Apply and select OK
18.Click Raster-Analysis-select DEM (Terrain models)
19.Give your filename in OUTPUT file using SELECT
20.Check your mode should be Hillshade and the click OK OK OK and close
21.You will get your output in sometime
```

# Practical 6: Working with Projections and WMS Data
```
1. Extract- Practical 5 data
2. Layer → Add Layer → Add Vector Layer
3. From the Practical 5 dataset → Select the file "ne_10m_admin_0_countries" and Open
4. Layer → Save As → Click on Browse and give it any names and Save
5. In CRS → Click on Symbol (Select CRS) (to the right side of the dropdown)
6. In Filter → give the value as 102008 and below From Coordinate Reference System → Select “North_America_Albers_Equal_Area_Conic” and click on OK-OK
7. Layer → Add Layer → Add Raster Layer
8. In Practical 5 folder → In the search bar search for *tif and select “MiniScale_(standard)_R17” click on Open and OK
9. In Project → Project Properties → CRS → In Filter give the value 102008 and below From Coordinate Reference System → Select “North_America_Albers_Equal_Area_Conic” and click on OK
```

## Part 2 Digitizing Map Data
```
1. Layers – Add Layers – Add Raster Layer – Select Christchurch Topo50 map.tif – ok
2. Right click on Christchurch Topo50 map – Select Properties – Pyramids – Select All pyramids – Click on build Pyramids – Apply – ok
3. Setting – Option – Digitizing – Default snap mode – To vertex and segment
4. Layer – Create Layer – New SpatialLite Layer – Database – Select Directory and give name – Type Line – Specify CRS as 4167 – Layer name Road – Attribute name – RoadName – Add to attribute list – Attribute name – RoadDesc – Add to attribute list – Ok
5. Toggle Editig – add line feature – plot line on map – Left click for plotting Right click to save
6. Right click on RoadDecs – Properties – Change Color – Increate Width – OK
7. Layer – Create Layer – New SpatialLite Layer – Type Polygon – Specify CRS as 4167 – Layer name Garden – Attribute name – GadernName – Add to attribute list – Ok
8. Toggle Editig – add polygon feature – plot polygon on map – Left click for plotting Right click to save
9. Right click on GardenName – Properties – Change Color – OK
10. Layer – Create Layer – New SpatialLite Layer – Type Point – Specify CRS as 4167 – Layer name Shop – Attribute name – ShopName – Add to attribute list – Ok
11. Toggle Editig – add point feature – plot point on map – Right click to save
12. Right click on ShopName – Properties – Change Color – Change Symbol – OK
```

# Practical 7: Working with Cartography

## Part 1
```
1. Layer -- add layer-- Add vector layer -- browse -- select "tl_2013_06_tract.zip" open -- open
2. Layer -- add layer -- add delimited text Layer -- select "ca_tracts_pop.csv" open
3. In file format select Csv (or custom delimiters will also work)
4. Geometry definition -- No geometry -- ok
5. Right click on "tl_2013_06_tract" properties – join --click on green adding icon(green plus icon)
6. Join field -- GEO.id2
7. Target Field -- GEOID -- ok -- apply -- ok
8. Right click on "tl_2013_06_tract" properties -- Style -- select single symbol -- dropdown -- graduated
9. Column -- select "ca_tracts_pop_D001" from drop down
10. Classes -- 6 and color ramp -- spectral
11. Mode Equal Interval then click on classify – apply --ok
```

## Part 2
```
1. Layer → Add Layer → Add Vector Layer
2. From the extracted data → Select the file "nybb.shp" and click on open
3. Layer → Add Layer → Add Vector Layer
4. Browse and open "OEM_Nursing_001.shp" file
5. Vector → Data Management Tools → Join attributes by location
6. In Target vector layer → select "nybb" file from the dropdown
7. In Output shapefile → Browse → Give a name to the file and save
8. In Output table → click on "Keep all records" click on OK - YES - OK
9. In the layers → Right click on the join file created in the output → Open Attribute Table (Check if the table is there or not and then close it)
10. Click on "Identify Features" symbol (from the above icons in the ribbon) and click on the map then the results will be seen in the "Identify results" to the left side of the screen
```