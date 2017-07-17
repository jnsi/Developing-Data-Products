# Developing Data Product Project week 2
Nsi J.  
17 juillet 2017  


# Context of the project    
- Create a web page using R Markdown that features a map created with Leaflet.
- Host your webpage on either GitHub Pages, RPubs, or NeoCities.


## Requirements of the project    
The webpage must contain the date that you created the document, and it must contain a map created with Leaflet. 


**Interactive map created on 17 July 2017 based on Christmas markets in France during 2016**     



```r
library(leaflet)
library(dplyr)
```

```
## 
## Attaching package: 'dplyr'
```

```
## The following objects are masked from 'package:stats':
## 
##     filter, lag
```

```
## The following objects are masked from 'package:base':
## 
##     intersect, setdiff, setequal, union
```

```r
# Date of the map
CreationDate <-date()
CreationDate
```

```
## [1] "Mon Jul 17 22:50:47 2017"
```

```r
XmasMarketIcon <- makeIcon(iconUrl="http://www.tappenbeck.net/osm/maps/icons/xmasmarket.png", iconWidth = 31*215/230, iconHeight = 31, iconAnchorX = 31*215/230/2, iconAnchorY = 16)

XmasMarketLatLong <- data.frame( lat = c(45.74766, 45.19294, 48.00028, 48.87489), lng = c(5.79714, 5.70925, 6.32449, -2.37669))


XmasMarketSites <- c( 
  "<a href='https://www.noel.org/Rhone-Alpes/Chambery'>Auvergne Place 
   Saint-Léger</a>", 
  "<a href='http://www.marches-noel.org/marche-de-noel-a-grenoble/'> Grenoble
   Place Du Docteur Martin</a>",
  "<a href='http://www.marchedenoel-plombieres.com/'>Grand Est Strasbourg </a>",
  "<a href='https://noel.org/Picardie/Saint-Sauveur-80/'> Saint-Helier Place
   Saint-Sauveur </a>"
                )

 XmasMarketLatLong %>% 
          leaflet() %>% 
          addTiles() %>% 
          addMarkers(icon = XmasMarketIcon, popup = XmasMarketSites)
```

<!--html_preserve--><div id="htmlwidget-4335a994c072d9c49843" style="width:672px;height:480px;" class="leaflet html-widget"></div>
<script type="application/json" data-for="htmlwidget-4335a994c072d9c49843">{"x":{"options":{"crs":{"crsClass":"L.CRS.EPSG3857","code":null,"proj4def":null,"projectedBounds":null,"options":{}}},"calls":[{"method":"addTiles","args":["//{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",null,null,{"minZoom":0,"maxZoom":18,"maxNativeZoom":null,"tileSize":256,"subdomains":"abc","errorTileUrl":"","tms":false,"continuousWorld":false,"noWrap":false,"zoomOffset":0,"zoomReverse":false,"opacity":1,"zIndex":null,"unloadInvisibleTiles":null,"updateWhenIdle":null,"detectRetina":false,"reuseTiles":false,"attribution":"&copy; <a href=\"http://openstreetmap.org\">OpenStreetMap<\/a> contributors, <a href=\"http://creativecommons.org/licenses/by-sa/2.0/\">CC-BY-SA<\/a>"}]},{"method":"addMarkers","args":[[45.74766,45.19294,48.00028,48.87489],[5.79714,5.70925,6.32449,-2.37669],{"iconUrl":{"data":"http://www.tappenbeck.net/osm/maps/icons/xmasmarket.png","index":0},"iconWidth":28.9782608695652,"iconHeight":31,"iconAnchorX":14.4891304347826,"iconAnchorY":16},null,null,{"clickable":true,"draggable":false,"keyboard":true,"title":"","alt":"","zIndexOffset":0,"opacity":1,"riseOnHover":false,"riseOffset":250},["<a href='https://www.noel.org/Rhone-Alpes/Chambery'>Auvergne Place \n   Saint-Léger<\/a>","<a href='http://www.marches-noel.org/marche-de-noel-a-grenoble/'> Grenoble\n   Place Du Docteur Martin<\/a>","<a href='http://www.marchedenoel-plombieres.com/'>Grand Est Strasbourg <\/a>","<a href='https://noel.org/Picardie/Saint-Sauveur-80/'> Saint-Helier Place\n   Saint-Sauveur <\/a>"],null,null,null,null,null,null]}],"limits":{"lat":[45.19294,48.87489],"lng":[-2.37669,6.32449]}},"evals":[],"jsHooks":[]}</script><!--/html_preserve-->

