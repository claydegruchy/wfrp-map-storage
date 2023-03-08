# WFRP Map storage
This is the storage area and sister repo to 
https://github.com/claydegruchy/wfrp-map-osm
This is used to store maps.

Thanks for storing my stuff github! Can you believe _they do it for free_?

# How to add to this
### First: Make sure the file is big and detailed!
- Get QGIS
- Get the plugin for QGIS: `Freehand raster georeferencer`
- Add the WFRP world as an external source either via gitzmans (http://www.gitzmansgallery.com/tiles/{z}_{x}_{y}.jpg) or this repo (https://claydegruchy.github.io/wfrp-map-storage/world-map/{Z}/{Z}_{X}_{Y}.jpg)


### Now we need to convert the image that we have to a georeferenced TIFF
- Use `Freehand raster` to import the file you want (`AD`)
- Postion it using the pokey ass interface it gives you (I suggest using `2P`)
- One in place, export and choose a dir


### Now we convert our georeferenced TIFF to XYZ chunks for easy usage in the main map
- Import the image into QGIS (I drag and drop into the panel), it should automatically sit in the right spot
- Unselect the other layers and enable the toolbox (processing>toolbox)
- Choose `gdal2tiles` 
- Set the settings, I use 
	- cutting profile = raster
	- zoom levels = 1-7 (1-8 for really big files)
	- web viewer = openlayers
	- title = title
	- output dir = somewhere obvious
	- It should look like this: `gdal2tiles.bat -p raster -z 1-7 -w openlayers -t Nuln -r average -a 0.0 source.png dest/`
- Set an output directory for the files AND the html
And its done

# Credits
I DO NOT OWN these maps and I give credit to the original authors:
## World map
Big thanks to gitzmansgallery for putting it together. Extract from gitzmansgallery.com:
Some original artwork is credited to Andreas Blicher, based upon Alfred Nunez, Jr.'s outstanding cartography and research. Many other sources were used including those from the Warhammer Maps page.

## City maps

### Altdorf
Thanks to Magnus Seter via http://altdorfer.blogspot.com. I hope to load the various POIs one day.

### Various maps from planjanusza
Big thanks to https://www.deviantart.com/planjanusza for the free listed assets on their deviantart. Amazing stuff and inspired me to make this. Multiple maps are used from here and I hope this list is exhaustive:
- Marienburg