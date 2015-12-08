# Zip_Backfill

The primary file is Zip_Backfill.py, all other files are to test its accuracy.

Zip_Backfill runs from the command line and takes as input two files: input and output. Input is a .csv file with addresses that need to be backfilled. This file should be in the format: Lon, Lat, Number, Street, City, District, Region, Zip, ID. Output is a .csv file that the backfilled addresses will be written into. Address rows will be returned in the same format as they are inputted.

##Dependencies

###All

- Python 2.7

###Zip_Backfill.py

- Fiona (Python Library)

- Shapely (Python Library)

- A census [ZCTA](https://www.census.gov/geo/reference/zctas.html) .shp file (the TIGER file can be found [here](ftp://ftp2.census.gov/geo/tiger/TIGER2015/ZCTA5/))

###Google_Check.py

- Requests (Python Library)

- A file with a valid Google API key or a valid Mapbox API key


##Accuracy

Running the included test file of 36 rows, three rows per state for three states in each of the four OpenAddresses areas, and using the Census Tiger ZCTA .shp file:

- 30/36 are found and backfilled with zip codes
- 27/30 of the backfilled zip codes agree with what the Google api returns as the zip code

Rows randomly picked from all files and using the Census Tiger ZCTA .shp file:

- 11,148/13,000 = 86%: backfilled

- 1,608/1,750 = 92%: agree with Google api

- 8587/8593 = 99% agree with Mapbox api



