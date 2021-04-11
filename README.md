# Overview

This repo contains the code, epubs, and images I used to create these print books based on Scott Alexander's writing: [SlateStarCodex Abridged](https://www.lulu.com/en/us/shop/scott-alexander/the-goddess-of-everything-else/paperback/product-j6d7wv.html?page=1&pageSize=4), [The Library of Scott Alexandria](https://www.lulu.com/en/us/shop/scott-alexander/the-library-of-scott-alexandria/hardcover/product-8dm4m8.html?page=1&pageSize=4), and [The Goddess of Everything Else](https://www.lulu.com/en/us/shop/scott-alexander/the-goddess-of-everything-else/paperback/product-j6d7wv.html?page=1&pageSize=4). Note that my code in epub_editing.ipynb very much does not run end-to-end. It's mostly little code snippets that I found helpful.

## Getting an epub

If you want to create a new epub from raw html files, you should use [pandoc](https://pandoc.org/). The command will be something like `f"pandoc --from html -o ssc_fiction.epub  --epub-metadata meta/slatestarcodex.fiction.xml  {html_paths}"`. To get the html files, I'd highly recommend [webpages-to-ebook](https://github.com/georgjaehnig/webpages-to-ebook). For now I'll assume you already have an epub, like the ones I put under resources (those epubs are special because Alexis Clay and I removed hundreds of typos!!)

## epub to pdf

To print a book, you'll need a pdf, not an epub. To convert to pdf I used calibre. There are several things that calibre lets you do while converting.

1. You can change the cover image by right clicking on it and going to 'edit metadata'
2. Most importantly, you'll want to convert to a pdf. Right click and go to 'convert book'.
2a. select pdf in the upper right
2b. under pdf output add page numbers, change the font to cambria (it's important to use a serif font), and set the custom size to 6 x 9 inches (for a small paperback). The default should be fine for a large book like SSC Abridged.
2c. under page setup select default output profile. Also make the margins all 36-72 pt (make sure the sizing is consistent with the pdf you used to get page numbers!)

Now that we have page numbers (ugh), we can add them to the table of contents, and then repeat the whole epub-to-pdf conversion. I have some code in my jupyter notebook which helps with reading the pdf for page numbers and editing files in the epub's table of contents to include those page numbers (this step is still pretty manual and involves calibre, oh well).

## pdf to print book

I use Lulu for printing. $44 for a hardcover, color book that's *half a million words* seems like a pretty great deal to me. For cover design, I normally use one of their default templates e.g. see the Goddess image I uploaded under resources/Goddess. I put that image together using some beautiful public domain art from pixabay and the photo editor Gimp.