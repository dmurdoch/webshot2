webshot2
========

**webshot2** is meant to be a replacement for [webshot](https://wch.github.io/webshot/), except that instead of using PhantomJS, it uses headless Chrome via the [Chromote](https://github.com/rstudio/chromote) package.


## Installation

webshot2 currently depends on a number of in-development packages.

This build includes a patch https://github.com/rstudio/webshot2/pull/21, so has been
set to version number 0.0.0.9000.21.  You can install just
the patched version, without the version number change,
using

```R
remotes::install_github("dmurdoch/webshot2@fixlockup")
```

Once that patch (or a better one) is merged into the main 
branch, you could use this code to install:

```R
remotes::install_github("rstudio/webshot2")
```

You also need to have the Chrome browser installed on your system. You can also use other browsers based on Chromium, such as Chromium itself, Edge, Vivaldi, Brave, or Opera.


## Usage

```R
library(webshot2)

# Single page
webshot("https://www.r-project.org")

# Multiple pages (in parallel!)
webshot(c("https://www.r-project.org", "https://www.rstudio.com"))

# Specific height and width
webshot("https://www.r-project.org", vwidth = 1600, vheight = 900, cliprect = "viewport")
```

