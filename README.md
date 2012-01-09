This is jsut a repo to keep track of converted data,
and I often need this sort of data.

I downloaded the shapefile from here:

http://www.naturalearthdata.com/downloads/110m-cultural-vectors/

Then, using OGR2OGR, I converted to a CSV with WKT.

* I unzipped the file as we need the .shp file
* I used `brew install gdal` to get ogr2ogr on Mac)

`ogr2ogr -f CSV 110m-admin-0-countries.csv 110m-admin-0-countries/ne_110m_admin_0_countries.shp -t_srs "EPSG:4326" -lco "GEOMETRY=AS_WKT" -lco "LINEFORMAT=CRLF" -lco "SEPARATOR=SEMICOLON"`

The SEMICOLON is important as WKT often contains commas.