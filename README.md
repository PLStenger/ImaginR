
[![CRAN_Status_Badge](https://www.r-pkg.org/badges/version/ImaginR)](https://cran.r-project.org/package=ImaginR) [![CRAN_Release_Date](https://www.r-pkg.org/badges/ago/ImaginR)](https://cran.r-project.org/package=ImaginR)
[![Downloads](https://cranlogs.r-pkg.org/badges/grand-total/ImaginR)](https://cran.r-project.org/package=ImaginR)

## Delimit and analyse color hues & color variations with `ImaginR`

<div align="center">
<img src="https://github.com/PLStenger/ImaginR/blob/master/logo_imaginr.png" width="250" height="250">
</div>

## Install from CRAN:
`install.packages("ImaginR")`

## Install from Github: (much more up to date)

    install.packages("devtools")
    library(devtools)
    install_github("PLStenger/ImaginR")
    library("ImaginR")

    # If "Error in fetch(key) : lazy-load database "
    # Run:
    .rs.restartR()


## Quick start
Put all your pictures in one folder. 

Open R. 

`setwd()` in the folder with the pictures.

Run the main fonction is `OutPutResult()`. 

Let's see the results !

Warning: If you need to redo analysis, please delete or change the name of the both OutPutAnalysis.txt and results.csv files in order to avoid confrontations.


## I) Analysing color phenotype and their variations on Pearl oyster *Pinctada margaritifera* (Linnaeus, 1758) with `ImaginR`
An R Package to delimit the color phenotype of the pearl oyster's inner shell (Pinctada margaritifera) and to characterize there color variations (by the HSV color code system).

The pearl oyster, *Pinctada margaritifera*, represents the second economic resource of French Polynesia.
It is one of the only bivalves expressing a large varied range of inner shell color, and by correlation, of pearl color.
This phenotypic variability is partly under genetic control, but also under environmental influence.
With `ImaginR`, it's now possible to delimit the color phenotype of the pearl oyster's inner shell and to characterize their color variations (by the HSV color code system) with pictures.

To see some color phenotype, go to https://plstenger.github.io/

![alt tag](https://github.com/PLStenger/ImaginR/blob/master/pmarg.png)

## For more details see the publication of ImaginR in the Scientific report journal here:
https://www.nature.com/articles/s41598-019-43777-4


## II) Update 06/12/2020 : Using `ImaginR` for fluorescent microscope images.

If you have already use old `ImaginR` version on your current analysis, please, save your work, quit R and R Studio. Re-open your file, don't run `ImaginR`, don't use the `ImaginR` CRAN version, because it wasn't already up-to-date. Please, install the new version from github:

    install.packages("devtools")
    library(devtools)
    install_github("PLStenger/ImaginR")
    library("ImaginR")

Then put your pictures in a folder, and set your working directory on it with `setwd()` or scroll with the R studio finder on the right to found the folder, clic on the button from R Studio on the right 'more' and then clic on 'Set As Working Directory'.

Only for fluorescent microscope images with black background, run this function (without anaything into the brackets):

`OutPutResult_microscopy()`

Normally, two files will be created into your folder (if your pictures are heavy, and.or if you have a lot of pictures, this could be take time (depend alos of your computer RAM power).
The first, the 'OutPutAnalysis_microscopy.txt' file is the raw results, and the second file, "results_microscopy.csv", is your results with the picture's names (warning: the header is shifted, will be fixed later).

## III) Update 04/05/2021 : Using `ImaginR` for measure forest cover images.

![alt tag](https://github.com/PLStenger/ImaginR/blob/master/forest_cover.png)

Obtain the forest cover by comparing two images with the `Forest_cover(x, y)` new function :
- the first picture (`x`, corresponding to the left image, named "A1_DJI_0026_cleaned_empty_before.JPG") is the original (aerial) image and 
- the second picture (`y`, corresponding to the right image, named "A1_DJI_0026_cleaned_empty.JPG") is the same image but without the soil (only forest cover is keep, with Gimp for example).

ex : 

      Forest_cover("A1_DJI_0026_cleaned_empty_before.JPG", "A1_DJI_0026_cleaned_empty.JPG")
      [1] 26.82175

Actually, the number of pixels from the second picture (`y`) is divided by the number of the first picture (`x`) and the result is put in percentages.
Here, in this example, the open low maquis is covering 26.82% of the area.

