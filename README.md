# R-package Tutorial

While there are already excellent materials available for creating an R package, such as Hadley Wickham's [R Packages](https://r-pkgs.org/introduction.html) book, this repository aims to help individuals create an R package with the least number of steps possible. Although achieving higher proficiency may require utilizing additional resources from the book, this tutorial serves as a concise starting point.

<img src="https://r-pkgs.org/images/cover-2e-small.png" width="200" alt="R Packages Book Cover">

## Prerequisites

Before diving into the package creation process, ensure you have the following prerequisites installed:

1. **R**: You'll need an up-to-date version of R installed on your system. You can download it from the official [R Project](https://www.r-project.org/) website.

2. **RStudio (Optional)**: Although not strictly required, using RStudio as your integrated development environment (IDE) is highly recommended for a smoother package development experience. You can download it from the [RStudio](https://www.rstudio.com/products/rstudio/download/) website.

## Getting Started

To begin creating your R package, follow these steps:

**1. Install devtools**: The `devtools` package is a vital tool for package development in R. Install it by running the following command in your R console:

```r
   install.packages("devtools")
```

**2. After installation, load the devtools package:**

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

**3. roxygen Comments**

Another important aspect that users need to know is the use of roxygen comments, which are different from the comments that R users are typically accustomed to. <br>

The following is a must-know list of roxygen comments: <br>

`@title`: Provides the title of the package <br>
`@description`: Describes the package <br>
`@param`: Documents the function arguments <br>
`@export`: Exports the function for use in other packages <br>
`@import`: Imports an entire package for use <br>
`@importFrom`: Imports specific functions from a package <br>
`@return`: Describes the return value of a function <br>

______________________________________
## Let's Start Making the Package

1. `usethis::use_r("my_pkg")` # Creates an R file called 'my_pkg.R' for your package

2. Add the roxygen documentation by pressing `Cmd + Shift + P` (or `Ctrl + Shift + P` on Windows) and selecting "Insert Roxygen Skeleton" in RStudio. This will add the necessary roxygen comments for your functions.

3. Add your function or commands that you want to be part of the package in the `my_pkg.R` file. Make sure to document them properly using roxygen comments.

4.  Use `devtools::document()` to update the package documentation based on the roxygen comments.
   *This command generates the help files and other documentation for your package. It's a good idea to run this after making changes to your code or documentation.*

5. Use `devtools::check()` to check your package for potential issues or errors.
   *This command will run a series of checks and provide feedback.*

6. Use `devtools::load_all()` to load the package code into your R session.
   *This allows you to test your functions and make sure they work as expected.*

7. Use `devtools::install()` to install the package from the local source.
   *This creates a binary package that can be loaded and used like any other R package.*

_________________

## Extra info 

### How to Upload an R Package to a GitHub Repository

Uploading your R package to GitHub can help you version control your work, collaborate with others, and share your package with the R community.

**1. Create a GitHub Account**
If you don't already have a GitHub account, you'll need to create one. Visit [GitHub's website](https://github.com/) and sign up.

**2. Create a New Repository**
- Once logged in to GitHub, click the "+" icon in the top right corner and select "New repository".
- Name your repository. It's common practice to name your repository after your R package.
- Optionally, add a description for your repository.
- Choose whether the repository will be public or private.
- Initialize the repository with a README, .gitignore (select R from the dropdown), and a license if you wish.
- Click "Create repository".

**3. Set Up Git Locally**
If you haven't already configured Git on your computer, open a terminal or command prompt and set up your user name and email address with the following commands:

```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```

**4. Clone the Repository to Your Local Machine**
Navigate to your newly created GitHub repository.
Click the "Code" button and copy the repository URL.
Open a terminal or command prompt, navigate to where you want to store your project, and clone the repository with:

```bash
git clone <repository-URL> #Replace <repository-URL> with the URL you copied.
```

**5. Add Your R Package to the Repository**
Move your R package files into the cloned repository directory on your local machine.
Open a terminal or command prompt and navigate to your repository directory.

**6. Commit Your R Package to Git**

```bash
git add .
git commit -m "Initial commit of my R package"
git push origin master
```

## Other key commands to advance your R-package 

```r
devtools::build_site() # Builds a package website; useful for generating documentation from RMarkdown files and roxygen2 comments.

usethis::use_test_that() # Initializes testing infrastructure using the 'testthat' framework in your R package. It creates tests/testthat directory and adds a dependency on 'testthat'.

usethis::use_test() # Creates a test file in 'tests/testthat' for a specified R function. You'll typically pass the name of the function you're writing tests for.

usethis::use_package() # Adds a specified package to the DESCRIPTION file's Imports or Suggests field, depending on your needs. Useful for declaring package dependencies.

usethis::use_version() # Incorrectly typed as 'use_versioh'. It should be 'use_version()'. This function helps you increment version number of your package in the DESCRIPTION file according to semantic versioning.
```



