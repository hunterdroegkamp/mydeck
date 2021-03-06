---
title       : Developing Data Products Project
subtitle    : Shiny App Pitch
author      : Hunter Droegkamp
job         : 
framework   : landslide     # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Predict Magnitude of Earthquakes off Fiji

The Shiny app attached to this project is designed to create a predictive model based on the 'quakes' dataset in R.

### Author

Hunter Droegkamp

### Date

8/13/17

--- .class #id 

## Details

The app allows prediction of the magnitude of earthquakes in Fiji based on the depth the earthquake was recorded at.

The depth can be adjusted using a slider to select a depth of 40 to 680 feet.

The linear model can then be visualized with a graph that shows a toggleable line of the model as well as points of the prediction and bounds of the prediction interval.

Numbers of the predictions will also appear below the graph.

--- .class #id

## App Functions

* Interactive graph with prediction model
* Depth slider
* Show/Hide model checkbox
* Numeric predictions
* readme info

--- .class #id

## Example
### Using Depth of 200 ft


```r
mdl <- lm(mag ~ depth, data = quakes)
mdlpred <- predict(mdl, newdata = data.frame(depth = 200), interval = "prediction")
print("Predicted Magnitude")
print(mdlpred[,1])
print("Lower Bound")
print(mdlpred[,2])
print("Upper Bound")
print(mdlpred[,3])
```

--- .class #id

## Example
### Using Depth of 200 ft


```
## [1] "Predicted Magnitude"
```

```
## [1] 4.6684
```

```
## [1] "Lower Bound"
```

```
## [1] 3.898457
```

```
## [1] "Upper Bound"
```

```
## [1] 5.438343
```
