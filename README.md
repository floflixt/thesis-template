# Thesis Template

This is a template for a thesis or a large report, based on RMarkdown `*.Rmd`-files.

It could definitely be improved (and will be in the future), since this evolved during the time I wrote my thesis - I did focus on other things;)

You can find my thesis that I created with this template here (click the PDF button): ![my thesis on my website](https://florif.github.io/publication/bachelor-thesis/)

## Basic Usage

1. Define the sections of your thesis in the main file, thesis.Rmd, like e.g., the section 'Abstract' by inserting the `R` code `R {r child='filepath.Rmd'}`. Note that those files should either be `*.Rmd` files (if you want to include content, text, images, ...) or `*.R` scripts, if you want to run an analysis at this location.
2. Add the content of each page in the content folder. For every main section, I used a separate file to keep everything clean (and I did version control using github). This way, you can create a PDF file for your supervisor even if you only worked on the methods section, for example. By the way: I highly recommend using git or some other version control for your thesis.
In the content folder, I also placed my analysis scripts (in Rmd). The data of the experiment was in the data folder.
3. Using the settings print_analysis and print_analysis_results you can decide if you want your analyses printed in your document. I found this useful for testing. These settings can be found in `thesis.Rmd`.
4. At any place in the document, you can access the variables from such a script like shown in the discussion section. This is only possible because the scripts are written in RMardown. But it is very easy to change any R script into a valid Rmd file.

## Notes

This is not yet a full documentation of this template, this is rather just the rough and dirty skeleton of my thesis. However, if you ever worked with LaTeX, you can adapt everything. You could also set `keep_latex: true`, so you can manually adjust everything that does not look right.

Using this template, you can generate **dynamic reports/theses**. So if you change a small thing in the data or analyses, it is possible to be directly transferred into the text. This forces you to split time-expensive analyses (reading much data, preprocessing) into a heavy script that you can run by hand once and that saves the results in, for example, .RDS binary files. Those can then be the input for the analysis Rmd scripts that do no heavy analyses (t-tests, plotting).

Since knitting/using rmarkdown requires you to have a LaTeX-Distribution installed, I recommend MikTex. It allows you to install every package you may need (and that you do not yet have installed) to be downloaded and installed automatically, and it can even ask you to decide on each package on its own.

You might want to add/remove some `\newpage` commands at the beginning to correctly position the pages on the left/right side of a page.

You can edit anything. You can add/remove sections, title pages, etc. 

Styling and the content of the title page happens in `style/title.sty` (I wanted a very beautiful title page, so I had to do this in Tex and not in Markdown. You can of course decide to use a markdown title page.)

Should be able to be knitted via the 'Knit' button in RStudio (not tested!) or using
`rmarkdown::render('thesis.Rmd', output_format = 'pdf_document', encoding = 'UTF-8')`. **Please try this before you start using this template! You might need to install the R package rmarkdown and some LaTeX packages.** At some point I will add a script or something similar to do this for you. I set up Sublime Text 3 (the text editor I use) to recompile the whole stuff by pressing 'CTRL + B' while editing the thesis.Rmd file.