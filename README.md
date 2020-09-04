## R Guide for the MSU SpaCE Lab 

**https://SpaCE-Lab-MSU.github.io/r_guide**

 * Phoebe Zarnetske, [SpaCE Lab: Spatial and Community Ecology Lab @ Michigan State University](http://www.communityecologylab.com/)
 * Patrick Bills, SpaCE Lab and MSU Analytics and Data Services 
 * add your name here!

This is our guide for writing and using R for collaborative projects in Community Ecology.  This of course is a work in progress and we welcome contributions.  

This is written in a form of [RMarkdown](https://r4ds.had.co.nz/r-markdown.html) using the [bookdown](https://github.com/rstudio/bookdown)  package to generate a website, and hosted on Github pages (see link above)

### Contributing

We need your help! We'd be delighted for you to want to contribute.  If so please don't  worry about getting the formatting, markdown, or bookdown correct.  Consider contributing even if you've never used the bookdown package.  We are interested in your ideas.  

If you want to quickly suggest content or just have a short idea or correction, you may submit a github issue to this project (see [Github.com:Creating an issue](https://help.github.com/en/github/managing-your-work-on-github/creating-an-issue) which requires a github account.   

If you want to edit files, clone or fork this repository.   

Then simply edit any one of the chapter files (Rmd files that begin with a two digit numeral) as you would edit an Rmarkdown file, or just add plain text.   If you want to add a new chapter, simply start a new Rmarkdown file, The first line of a new file must be code as a header with a single `#`  (e.g. `# Tracking Woozles`) which will be the chapter title.   IF there are any issues we are happy edit so your ideas can be incorporated.  

If you are a lab collaborator and have a found a successful technique we want to hear about it.   Consider a new chapter describing this and pointers to examples on github.  



## Pre-requisites for Working with Bookdown

You need a plain text editor that can create Markdown (we use Rstudio).  Word Processors insert unreadable characters (curly quotes).  When writing markdown ou can use anything that Pandoc's Markdown supports, e.g., a math equation $a^2 + b^2 = c^2$.

To render this book, you need the **bookdown** package fo rone.  This project uses the [renv](https://rstudio.github.io/renv/articles/renv.html) package to manage installation.   After cloning/downloading to your computer, you can install all the packages you need with 


```{r eval=FALSE}
install.packages("renv")
renv::init()
```

The bookdown may also require the pandoc utility.  On mac open the terminal install the [homebrew](https://brew.sh/) utility using their instructions,  and then  `install brew install pandoc`.   Needed: windows instructions for getting started.  

Each Rmd file contains one and only one chapter, and a chapter is defined by the first-level heading `#`.   Additional sub-headings ( prefaced with `##` or `###` ) inside the chaper file become entries in the table of contents.   

Once you've created a new chapter file, you must add it to the list of chapters in the file `_bookdown.yml`  in the `rmd_files` array.  Insert the filename of your chapter position you want it so show.   surrounded by quotes and always followed by a comma  `"mychapter.Rmd",`

For example to add `my_new_chapter.Rmd` : 

```
...
rmd_files: [
  "index.Rmd",
  
  "documentation.Rmd",
  "configuration.Rmd",
  "my_new_chaper.Rmd"
  "package_management.Rmd",
]
...
```

To compile this book (to HTML) use the R function `bookdown::render_book("index.Rmd", "bookdown::gitbook", output_dir = "docs")`in the R console.  The project is set to render the HTML into the 'docs' folder, and this github project is configured to serve the docs folder as a web page.   On your own computer, to preview and test that it compiled that way you want, in Rstudio open the file `docs/index.html` and select "with browser."   Once you get it the way you like, you can push both the Rmd files you've edited, and any files changed in the docs folder.  

Currently compilation to PDF or other formats is not enabled, as the work in initial development and PDF generation requires additional software that may be difficult to install.  In addition the use of citations/bibliography is not enabled but it can be if you'd like to use it.  Our goal is to make it easy to contribute by keeping it simple. 

To learn more about add PDF compilation and other features, see the bookdown documentation.  We could create a git branch that has this feature enabled. 
