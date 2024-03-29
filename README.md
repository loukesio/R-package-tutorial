# R-package Tutorial

While there are already excellent materials available for creating an R package, such as Hadley Wickham's [R Packages](https://r-pkgs.org/introduction.html) book, this repository aims to help individuals create an R package with the least number of steps possible. Although achieving higher proficiency may require utilizing additional resources from the book, this tutorial serves as a concise starting point.

<img src="https://r-pkgs.org/images/cover-2e-small.png" width="200" alt="R Packages Book Cover">

## Prerequisites

Before diving into the package creation process, ensure you have the following prerequisites installed:

1. **R**: You'll need an up-to-date version of R installed on your system. You can download it from the official [R Project](https://www.r-project.org/) website.

2. **RStudio (Optional)**: Although not strictly required, using RStudio as your integrated development environment (IDE) is highly recommended for a smoother package development experience. You can download it from the [RStudio](https://www.rstudio.com/products/rstudio/download/) website.

## Getting Started

To begin creating your R package, follow these steps:

1. **Install devtools**: The `devtools` package is a vital tool for package development in R. Install it by running the following command in your R console:

```r
   install.packages("devtools")
```

2. **After installation, load the devtools package:**

```
library(devtools)
```

You'll need additional commands from devtools to create and manage your package. Here are some essential commands:
```
devtools::install() # Install a package from a local source
devtools::load_all() # Load the package code into your R session
devtools::document() # Update the package documentation
devtools::check() # Check the package for potential issues
```

3. Roxygen Comments

Another important aspect that users need to know is the use of roxygen comments, which are different from the comments that R users are typically accustomed to. <br>

The following is a must-know list of roxygen comments: <br>

`@title`: Provides the title of the package
`@description`: Describes the package
`@param`: Documents the function arguments
`@export`: Exports the function for use in other packages
`@import`: Imports an entire package for use
`@importFrom`: Imports specific functions from a package
`@return`: Describes the return value of a function


## Let's Start Making the Package

1. `usethis::use_r("my_pkg")` # Creates an R file called 'my_pkg.R' for your package

2. Add the roxygen documentation by pressing `Cmd + Shift + P` (or `Ctrl + Shift + P` on Windows) and selecting "Insert Roxygen Skeleton" in RStudio. This will add the necessary roxygen comments for your functions.

3. Add your function or commands that you want to be part of the package in the `my_pkg.R` file. Make sure to document them properly using roxygen comments.

4. Use `devtools::check()` to check your package for potential issues or errors.
   *This command will run a series of checks and provide feedback.*

5. Use `devtools::load_all()` to load the package code into your R session.
   *This allows you to test your functions and make sure they work as expected.*

6. Use `devtools::document()` to update the package documentation based on the roxygen comments.
   *This command generates the help files and other documentation for your package. It's a good idea to run this after making changes to your code or documentation.*

7. Use `devtools::install()` to install the package from the local source.
   *This creates a binary package that can be loaded and used like any other R package.*
