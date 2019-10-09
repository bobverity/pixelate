# pixelate

An R package to pixelate spatial predictions according to the uncertainty that surrounds them.

<!--- e.g. ![ ](link-to-image) --->
<!--- I have not figured out how to export a single code chunck figure from the vignette
and load here since best practice dictates that vignettes should be built on installation;
see https://github.com/r-lib/devtools/issues/584. 
Perhaps we could add some static examples based not on pf. That way we can avoid the need to 
sync and thus avoid any conflict between images here in the manuscript / vugnette? 
---> 

## Prerequisites

The package **pixelate** is an R package. 
It was developed in R version 3.6.1 (2019-07-05) using RStudio. 
To download and install R please go to [cran.r-project.org](https://cran.r-project.org).
To download and install RStudio please go to [rstudio.com](https://rstudio.com/).

## Installation

A development version of **pixelate** is available on Github. 
It can be installed in R using `install_github` from the **devtools** package.
At the time of writing (9th Oct 2019), 
an in-development version of devtools (version ‘2.2.1.9000’)
was needed to build **pixelate**'s vignette (central to understading **pixelate**),
upon **pixelate**'s installation. 
Please follow the code below to ensure the vignette builds.  

_**Please be aware**_, installation with `build_vignettes = TRUE` takes several minutes 
(approximately 5 mins on a Macbook Pro) 
because the vignette includes plots that are slown to generate. 

<!--- (We chose `build_vignettes = TRUE` over removing `inst/doc` from .gitignore following 
Hadley Wickham's advice; see https://github.com/r-lib/devtools/issues/584). --->

```r
# Step 1) install devtools as required: 

if (!require("devtools")) { # If devtools is not intalled
  
  # Install stable version from CRAN:  
  install.packages("devtools") # Version ‘2.2.1’
  
  # Extract and compare its version: 
  vdetools = as.character(packageVersion("devtools"))
  vcompare = compareVersion(vdetools, '2.2.1.9000')
  
  if (vcompare < 0) {  # If the stable version is < ‘2.2.1.9000’
    
    # Install in-development version from Github
    devtools::install_github("r-lib/devtools") 
  }

} else { # If devtools is already intalled  
  
  # Extract and compare its version: 
  vdetools = packageVersion("devtools")
  vcompare = compareVersion(as.character(vdetools), '2.2.1.9000')
  
  if (vcompare < 0) { # If the stable version is < ‘2.2.1.9000’
    
    # Install in-development version from Github
    devtools::install_github("r-lib/devtools") 
  }
}


# Step 2) install pixelate from GitHub 
# Approximately 5 mins on a Macbook Pro with 2.7 GHz Intel Core i5
devtools::install_github("artaylor85/pixelate", build_vignettes = TRUE)
```

## Usage

The **pixelate** package centres around a single function `pixelate`.
To use `pixelate` and visualise its output following our examples, 
please install **ggplot2** if required and attach both packages as follows. 

```r
# Install ggplot2 from CRAN if required
if (!require("ggplot2")) install.packages("ggplot2") 

# Attach packages pixelate and ggplot2 
library(pixelate) 
library(ggplot2)
```

Thereafter, please read the **pixelate** vignette for quick and detailed examples of **pixelate**'s usage. 
The vignette can be accessed as follows. 

<!--- Avoid examples here s.t. user follows the vignette --->

```r
# Load vignette
vignette("pixelate")
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

<!--- Please make sure to update tests as appropriate. --->

## License
[MIT](https://choosealicense.com/licenses/mit/)

<!--- ## Acknowledgements 
Acknowledge everyone who helps test code (e.g. PM)
