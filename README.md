# Markdown Resume

This repo allows you to build/maintain your resume in a Markdown file, and then publish it into an HTML or PDF file. 

The inspiration for this project came from my need to look for a job, my need to update my resume, and my desire not to have to write something in Google docs, or Microsoft Word, so I scoured the web for newer way to build/maintain a resume, while doing so I ran into this [project by V Luther](https://vidluther.github.io/). 

I modified the CSS for my taste, and noticed that some of the documentation needed to be updated. 

# Workflow

The workflow is pretty simple. 

1. Edit the resume.md file. 
1. Run pandoc to convert the Markdown file to HTML. OR 
1. Run pandoc to convert the Markdown file into a PDF.


I also don't feel like supporting/using Microsoft Word, so I'm not even trying to output to .

# Pre-Requisites. 
## [Pandoc](https://pandoc.org) a universal document converter.

```bash 
    brew install pandoc 
```

## [Wkhtmltopdf](https://wkhtmltopdf.org)
```
    brew install wkhtmltopdf
```

## Markdown to HTML 
```
pandoc resume.md -f markdown -t html -c resume-stylesheet.css -s -o resume.html
```

## Markdown to PDF 

```
pandoc resume.md -f markdown -t pdf --pdf-engine=wkhtmltopdf -c resume-stylesheet.css -s -o resume.pdf
```

## HTML to PDF 

If you want to convert from HTML to PDF for some reason, you'll need to add a switch to wkhtmltopdf so that it works properly. 

```
wkhtmltopdf --enable-local-file-access resume.html resume.pdf
```

# TODO 
 - [x] [github action](https://github.com/pandoc/pandoc-action-example) will run and create the HTML and PDF file automatically. 
 - [ ] the Author field in the PDF, it seems to not work when the pdf-engine is set to wkhtmltopdf 
 - [ ] make a release or a package? 
