
# A new chapter

If you haven't yet read the getting started Wiki pages; [start there](https://www.ottrproject.org/getting_started.html).

To see the rendered version of this chapter and the rest of the template, see here: https://jhudatascience.org/OTTR_Template/.

Every chapter needs to start out with this chunk of code:




## Learning Objectives

Every chapter also needs Learning objectives that will look like this:  

This chapter will cover:  

- {You can use https://tips.uark.edu/using-blooms-taxonomy/ to define some learning objectives here}
- {Another learning objective}

## Libraries

For this chapter, we'll need the following packages attached:

*Remember to add [any additional packages you need to your course's own docker image](https://github.com/jhudsl/OTTR_Template/wiki/Using-Docker#starting-a-new-docker-image).


``` r
library(magrittr)
```

## Topic of Section

You can write all your text in sections like this, using `##` to indicate a new header. you can use additional pound symbols to create lower levels of headers.

See [here](https://www.rstudio.com/wp-content/uploads/2015/02/rmarkdown-cheatsheet.pdf) for additional general information about how you can format text within R Markdown files. In addition, see [here](https://pandoc.org/MANUAL.html#pandocs-markdown) for more in depth and advanced options.

### Subtopic

Here's a subheading (using three pound symbols) and some text in this subsection!

## Code examples

You can demonstrate code like this:


``` r
output_dir <- file.path("resources", "code_output")
if (!dir.exists(output_dir)) {
  dir.create(output_dir)
}
```

And make plots too:


``` r
hist_plot <- hist(iris$Sepal.Length)
```

<img src="resources/images/02-chapter_of_course_files/figure-html/unnamed-chunk-4-1.png" width="672" />

You can also save these plots to file:


``` r
png(file.path(output_dir, "test_plot.png"))
hist_plot
```

```
## $breaks
## [1] 4.0 4.5 5.0 5.5 6.0 6.5 7.0 7.5 8.0
## 
## $counts
## [1]  5 27 27 30 31 18  6  6
## 
## $density
## [1] 0.06666667 0.36000000 0.36000000 0.40000000 0.41333333 0.24000000 0.08000000
## [8] 0.08000000
## 
## $mids
## [1] 4.25 4.75 5.25 5.75 6.25 6.75 7.25 7.75
## 
## $xname
## [1] "iris$Sepal.Length"
## 
## $equidist
## [1] TRUE
## 
## attr(,"class")
## [1] "histogram"
```

``` r
dev.off()
```

```
## quartz_off_screen 
##                 2
```

## Image example

How to include a Google slide. It's simplest to use the `ottrpal` package:


<img src="resources/images/02-chapter_of_course_files/figure-html//1YmwKdIy9BeQ3EShgZhvtb3MgR8P6iDX4DfFD65W_gdQ_gcc4fbee202_0_141.png" alt="Major point!! example image" width="100%" style="display: block; margin: auto;" />

But if you have the slide or some other image locally downloaded you can also use HTML like this:

<img src="resources/images/02-chapter_of_course_files/figure-html//1YmwKdIy9BeQ3EShgZhvtb3MgR8P6iDX4DfFD65W_gdQ_gcc4fbee202_0_141.png" title="Major point!! example image" alt="Major point!! example image" style="display: block; margin: auto;" />

## Video examples
You may also want to embed videos in your course. If alternatively, you just want to include a link you can do so like this:

Check out this [link to a video](https://www.youtube.com/embed/VOCYL-FNbr0) using markdown syntax.

### Using `knitr`

To embed videos in your course, you can use `knitr::include_url()` like this:
Note that you should use `echo=FALSE` in the code chunk because we don't want the code part of this to show up. If you are unfamiliar with [how R Markdown code chunks work, read this](https://rmarkdown.rstudio.com/lesson-3.html).


<iframe src="https://www.youtube.com/embed/VOCYL-FNbr0" width="672" height="400px" data-external="1"></iframe>

### Using HTML

<iframe src="https://www.youtube.com/embed/VOCYL-FNbr0" width="672" height="400px"></iframe>

## File examples

You can again use simple markdown syntax to just include a link to a file like so:

[A file](https://www.bgsu.edu/content/dam/BGSU/center-for-faculty-excellence/docs/TLGuides/TLGuide-Learning-Objectives.pdf).

Alternatively you can embed files like PDFs.

### Using `knitr`

<iframe src="https://drive.google.com/file/d/1mm72K4V7fqpgAfWkr6b7HTZrc3f-T6AV/preview" width="100%" height="400px" data-external="1"></iframe>

### Using HTML

<iframe src="https://drive.google.com/file/d/1mm72K4V7fqpgAfWkr6b7HTZrc3f-T6AV/preview" width="672" height="800px"></iframe>

## Website Examples

Yet again you can use a link to a website like so:

[A Website](https://yihui.org)

You might want to have users open a website in a new tab by default, especially if they need to reference both the course and a resource at once.

[A Website](https://yihui.org){target="_blank"}

Or, you can embed some websites.

### Using `knitr`

This works:

<iframe src="https://yihui.org" width="672" height="400px" data-external="1"></iframe>


### Using HTML

<iframe src="https://yihui.org" width="672" height="400px"></iframe>


If you'd like the URL to show up in a new tab you can do this:

```
<a href="https://www.linkedin.com" target="_blank">LinkedIn</a>
```

## Citation examples

We can put citations at the end of a sentence like this [@rmarkdown2021].
Or multiple citations [@rmarkdown2021, @Xie2018].

but they need a ; separator [@rmarkdown2021; @Xie2018].

In text, we can put citations like this @rmarkdown2021.

## Stylized boxes

Occasionally, you might find it useful to emphasize a particular piece of information. To help you do so, we have provided css code and images (no need for you to worry about that!) to create the following stylized boxes.

You can use these boxes in your course with either of two options: using HTML code or Pandoc syntax.

### Using `rmarkdown` container syntax

The `rmarkdown` package allows for a different syntax to be converted to the HTML that you just saw and also allows for conversion to LaTeX. See the [Bookdown](https://bookdown.org/yihui/rmarkdown-cookbook/custom-blocks.html) documentation for more information [@Xie2020]. Note that Bookdown uses Pandoc.


```
::: {.notice}
Note using rmarkdown syntax.

:::
```

::: {.notice}
Note using rmarkdown syntax.

:::

As an example you might do something like this:

::: {.notice}
Please click on the subsection headers in the left hand
navigation bar (e.g., 2.1, 4.3) a second time to expand the
table of contents and enable the `scroll_highlight` feature
([see more](introduction.html#scroll-highlight))
:::


### Using HTML

To add a warning box like the following use:

```
<div class = "notice">
Followed by the text you want inside
</div>
```

This will create the following:

<div class = "notice">

Followed by the text you want inside

</div>

Here is a `<div class = "warning">` box:

<div class = "warning">

Note text

</div>

Here is a `<div class = "github">` box:

<div class = "github">

GitHub text

</div>


Here is a `<div class = "dictionary">` box:

<div class = "dictionary">

dictionary text

</div>


Here is a `<div class = "reflection">` box:

<div class = "reflection">

reflection text

</div>

Here is a `<div class = "wip">` box:

<div class = "wip">

This section is a **Work in Progress**.

</div>


## Dropdown summaries

<details><summary> You can hide additional information in a dropdown menu </summary>
Here's more words that are hidden.
</details>

## Print out session info

You should print out session info when you have code for [reproducibility purposes](https://jhudatascience.org/Reproducibility_in_Cancer_Informatics/managing-package-versions.html).


``` r
devtools::session_info()
```

```
## ─ Session info ───────────────────────────────────────────────────────────────
##  setting  value
##  version  R version 4.4.1 (2024-06-14)
##  os       macOS Ventura 13.6.1
##  system   aarch64, darwin20
##  ui       X11
##  language (EN)
##  collate  en_US.UTF-8
##  ctype    en_US.UTF-8
##  tz       America/New_York
##  date     2024-08-05
##  pandoc   3.1.11 @ /Users/tan/Applications/RStudio.app/Contents/Resources/app/quarto/bin/tools/aarch64/ (via rmarkdown)
## 
## ─ Packages ───────────────────────────────────────────────────────────────────
##  package     * version date (UTC) lib source
##  askpass       1.2.0   2023-09-03 [1] CRAN (R 4.4.0)
##  bookdown      0.40    2024-07-02 [1] CRAN (R 4.4.0)
##  bslib         0.8.0   2024-07-29 [1] CRAN (R 4.4.0)
##  cachem        1.1.0   2024-05-16 [1] CRAN (R 4.4.0)
##  chromote      0.2.0   2024-02-12 [1] CRAN (R 4.4.0)
##  cli           3.6.3   2024-06-21 [1] CRAN (R 4.4.0)
##  curl          5.2.1   2024-03-01 [1] CRAN (R 4.4.0)
##  devtools      2.4.5   2022-10-11 [1] CRAN (R 4.4.0)
##  digest        0.6.36  2024-06-23 [1] CRAN (R 4.4.0)
##  dplyr         1.1.4   2023-11-17 [1] CRAN (R 4.4.0)
##  ellipsis      0.3.2   2021-04-29 [1] CRAN (R 4.4.0)
##  evaluate      0.24.0  2024-06-10 [1] CRAN (R 4.4.0)
##  fansi         1.0.6   2023-12-08 [1] CRAN (R 4.4.0)
##  fastmap       1.2.0   2024-05-15 [1] CRAN (R 4.4.0)
##  fs            1.6.4   2024-04-25 [1] CRAN (R 4.4.0)
##  generics      0.1.3   2022-07-05 [1] CRAN (R 4.4.0)
##  glue          1.7.0   2024-01-09 [1] CRAN (R 4.4.0)
##  highr         0.11    2024-05-26 [1] CRAN (R 4.4.0)
##  hms           1.1.3   2023-03-21 [1] CRAN (R 4.4.0)
##  htmltools     0.5.8.1 2024-04-04 [1] CRAN (R 4.4.0)
##  htmlwidgets   1.6.4   2023-12-06 [1] CRAN (R 4.4.0)
##  httpuv        1.6.15  2024-03-26 [1] CRAN (R 4.4.0)
##  httr          1.4.7   2023-08-15 [1] CRAN (R 4.4.0)
##  janitor       2.2.0   2023-02-02 [1] CRAN (R 4.4.0)
##  jquerylib     0.1.4   2021-04-26 [1] CRAN (R 4.4.0)
##  jsonlite      1.8.8   2023-12-04 [1] CRAN (R 4.4.0)
##  knitr         1.48    2024-07-07 [1] CRAN (R 4.4.0)
##  later         1.3.2   2023-12-06 [1] CRAN (R 4.4.0)
##  lifecycle     1.0.4   2023-11-07 [1] CRAN (R 4.4.0)
##  lubridate     1.9.3   2023-09-27 [1] CRAN (R 4.4.0)
##  magrittr    * 2.0.3   2022-03-30 [1] CRAN (R 4.4.0)
##  memoise       2.0.1   2021-11-26 [1] CRAN (R 4.4.0)
##  mime          0.12    2021-09-28 [1] CRAN (R 4.4.0)
##  miniUI        0.1.1.1 2018-05-18 [1] CRAN (R 4.4.0)
##  openssl       2.2.0   2024-05-16 [1] CRAN (R 4.4.0)
##  ottrpal       1.3.0   2024-08-05 [1] Github (jhudsl/ottrpal@6fe8e03)
##  pillar        1.9.0   2023-03-22 [1] CRAN (R 4.4.0)
##  pkgbuild      1.4.4   2024-03-17 [1] CRAN (R 4.4.0)
##  pkgconfig     2.0.3   2019-09-22 [1] CRAN (R 4.4.0)
##  pkgload       1.4.0   2024-06-28 [1] CRAN (R 4.4.0)
##  processx      3.8.4   2024-03-16 [1] CRAN (R 4.4.0)
##  profvis       0.3.8   2023-05-02 [1] CRAN (R 4.4.0)
##  promises      1.3.0   2024-04-05 [1] CRAN (R 4.4.0)
##  ps            1.7.7   2024-07-02 [1] CRAN (R 4.4.0)
##  purrr         1.0.2   2023-08-10 [1] CRAN (R 4.4.0)
##  R6            2.5.1   2021-08-19 [1] CRAN (R 4.4.0)
##  Rcpp          1.0.13  2024-07-17 [1] CRAN (R 4.4.0)
##  readr         2.1.5   2024-01-10 [1] CRAN (R 4.4.0)
##  remotes       2.5.0   2024-03-17 [1] CRAN (R 4.4.0)
##  rlang         1.1.4   2024-06-04 [1] CRAN (R 4.4.0)
##  rmarkdown     2.27    2024-05-17 [1] CRAN (R 4.4.0)
##  rprojroot     2.0.4   2023-11-05 [1] CRAN (R 4.4.0)
##  rstudioapi    0.16.0  2024-03-24 [1] CRAN (R 4.4.0)
##  sass          0.4.9   2024-03-15 [1] CRAN (R 4.4.0)
##  sessioninfo   1.2.2   2021-12-06 [1] CRAN (R 4.4.0)
##  shiny         1.9.1   2024-08-01 [1] CRAN (R 4.4.0)
##  snakecase     0.11.1  2023-08-27 [1] CRAN (R 4.4.0)
##  stringi       1.8.4   2024-05-06 [1] CRAN (R 4.4.0)
##  stringr       1.5.1   2023-11-14 [1] CRAN (R 4.4.0)
##  tibble        3.2.1   2023-03-20 [1] CRAN (R 4.4.0)
##  tidyselect    1.2.1   2024-03-11 [1] CRAN (R 4.4.0)
##  timechange    0.3.0   2024-01-18 [1] CRAN (R 4.4.0)
##  tzdb          0.4.0   2023-05-12 [1] CRAN (R 4.4.0)
##  urlchecker    1.0.1   2021-11-30 [1] CRAN (R 4.4.0)
##  usethis       3.0.0   2024-07-29 [1] CRAN (R 4.4.0)
##  utf8          1.2.4   2023-10-22 [1] CRAN (R 4.4.0)
##  vctrs         0.6.5   2023-12-01 [1] CRAN (R 4.4.0)
##  webshot2      0.1.1   2023-08-11 [1] CRAN (R 4.4.0)
##  websocket     1.4.2   2024-07-22 [1] CRAN (R 4.4.0)
##  xfun          0.46    2024-07-18 [1] CRAN (R 4.4.0)
##  xml2          1.3.6   2023-12-04 [1] CRAN (R 4.4.0)
##  xtable        1.8-4   2019-04-21 [1] CRAN (R 4.4.0)
##  yaml          2.3.10  2024-07-26 [1] CRAN (R 4.4.0)
## 
##  [1] /Users/tan/Library/R/arm64/4.4.ottr
##  [2] /Library/Frameworks/R.framework/Versions/4.4-arm64/Resources/library
## 
## ──────────────────────────────────────────────────────────────────────────────
```

[many links]: https://github.com/jhudsl/OTTR_Template
