# Geospatial analysis of effectiveness of digital intervention in the rural U.S.


In this project, I visualized data to investigate the effectiveness of utilizing social media-based advertisements and content for the purpose of involving rural adolescents experiencing increased depression symptoms in a randomized trial examining single-session interventions.

<!--more-->

## 1 Overview

{{< admonition tip "Problem that I tried to solve:" >}}
Using data from [a previously-completed clinical trial](https://osf.io/8mk6x/), I was curious does instagram-based recruitment led to nationally-representative samples of youth living in both rural and urban area in the U.S.?
{{< /admonition >}}

## 2 Workflow

* apple-touch-icon.png (180x180)
* favicon-32x32.png (32x32)
* favicon-16x16.png (16x16)
* mstile-150x150.png (150x150)
* android-chrome-192x192.png (192x192)
* android-chrome-512x512.png (512x512)

## 3 Visualization & Analysis!

### 3-1 Visualization 

In this project, I utilized the maps package to obtain comprehensive U.S. map data, encompassing information on continents, countries, and states. Subsequently, I employed the geom_polygon() function from the ggplot2 package to create a detailed visualization of the U.S. map, which included the delineation of regional boundaries.

The project's repository is: https://github.com/yamachang/cope_rurality.

Please open the code block below to view the code for using `ggplot()` to create a U.S. map here :(far fa-hand-point-down fa-fw)::

```r
### Plotting!

plot_rucc2013 <- ggplot(map_df_usa1, aes(x = Longitude, y = Latitude, group = group)) +
  geom_polygon(aes(fill = rucc_2013)) +
  scale_fill_continuous(name = "Urbanicity in the U.S.", low = "darkblue", 
            high = "lightblue", limits = c(0,10), breaks = c(1,9), 
            labels = c("Urban Area (>250K)","Rural Area (<2.5K)"),
            na.value = "grey50") +
  geom_path(data = map_state1, colour = "white", size= .1) +
  geom_point(data = map_of_participants_3, mapping = aes(x = Longitude, y = Latitude, shape = as.factor(rucc_bi)), size = 0.85, color = "gold", alpha = 0.8) + 
  scale_shape_discrete(name = "Participants", labels = c("Urban Area","Rural Area")) + 
  coord_quickmap() +
  theme(legend.margin = margin(t = 0, r = 20, b = 0, l = 20, unit = "pt"),
        plot.margin = margin(t = 0, r = 0, b = 0, l = 20, unit = "pt"))
        
```
### 3-2 Analysis

## 4 What I learned




