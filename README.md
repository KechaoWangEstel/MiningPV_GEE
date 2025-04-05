# MiningPV_GEE

All the TXT files store JavaScript code from Google Earth Engine. Specifically:

### MergeMiningBoundary_getPointwithArea

This code takes the union of the global open - pit mining patch vector boundaries from Maus and Tang. It then calculates the sum of the areas of bare land and construction land within each polygon after the union operation. The area attribute is assigned to the centroid point of each polygon.

### MinesStatus

This code is used for classifying the types of global open - pit mining polygons based on NDVI.

### getPVPoints

This code finds the center points of global photovoltaic panel vectors and generates circular buffer zones to create negative samples for training. During the process of generating negative samples, the negative sample points that fall on water bodies and other photovoltaic panels are removed.

### getRoadDis

Using the GRIP4 road vector data, this code calculates the shortest distances from each point to the nearest highways and main roads. The results are output as environmental variables for subsequent training.

### getParams

This code collects environmental variables for training. It obtains environmental variable parameters for each point and finally merges them into a CSV file for export. Subsequently, the data will be used for RANN construction and training in a local Python environment.
