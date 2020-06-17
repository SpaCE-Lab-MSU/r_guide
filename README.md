## R Guide for the MSU SpaCE Lab

 * Phoebe Zarnetske, [SpaCE Lab: Spatial and Community Ecology Lab @ Michigan State University](http://www.communityecologylab.com/)
 * Patrick Bills, SpaCE Lab and MSU Analytics and Data Services 
 * add your name here...

This is a guide for writing and using R for collaborative projects in Community Ecology.  This of course is a work in progress and we welcome contributions.  

This is written in a form of [RMarkdown](https://r4ds.had.co.nz/r-markdown.html) using the package  [bookdown](https://github.com/rstudio/bookdown) to generate a website, and hosted on Github pages. 

We are delighted if you want to contribute and don't want you to worry about formatting or bookdown tricks, so consider contributing even if you've never used the bookdown package.     We are interested in your ideas.   Simply edit any one of the chapter files (Rmd files that begin with a two digit numeral) as you would edit an Rmarkdown file, or just add plain text.   If you want to add a new chapter, simply start a new Rmarkdown file, The first line of a new file must be code as a header with a single `#`  (e.g. `# Tracking Woozles`) which will be the chapter title.   IF there are any issues we are happy edit so your ideas can be incorporated.  

If you are a lab collaborator and have a found a successful technique we want to hear about it.   Consider a new chapter describing this and pointers to examples on github.  

Alternatively if you are unsure or just have a short idea or correction, you may submit a github issue to this project (see [Github.com:Creating an issue](https://help.github.com/en/github/managing-your-work-on-github/creating-an-issue) which requires a github account.   



## Prerequisites

You need a plain text editor that can create Markdown (we use Rstudio).  Word Processors insert unreadable characters (curly quotes).  When writing markdown ou can use anything that Pandoc's Markdown supports, e.g., a math equation $a^2 + b^2 = c^2$.

To render this book, you need the **bookdown** package, which can be installed from CRAN or Github:

```{r eval=FALSE}
install.packages("bookdown")
# or the development version
# devtools::install_github("rstudio/bookdown")
```

it may also require the pandoc utility.  On mac open the terminal install the [homebrew](https://brew.sh/) utility using their instructions,  and then  `install brew install pandoc` .   Needed: windows instructions for getting started.  

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

To compile this book to HTML to test that simply issue the command `bookdown::render_book("index.Rmd", "bookdown::gitbook", output_dir = "docs")`  The project is set to render the HTML into the 'docs' folder.  The github project is configured to serve the docs folder as a web page.   To preview it open the file `docs/index.html` with your web browser. 

Currently compilation to PDF or other formats is not enabled as the work in initial development and PDF generation requires additional software that may be difficult to install.  In addition the use of citations/bibliography is not enabled but it can be if you'd like to use it.  Our goal is to make it easy to contribute by keeping it simple. 

To learn more about add PDF compilation and other features, see the bookdown documentation.  We could create a git branch that has this feature enabled. 
