---
date: "2020-05-18"
title: How to add a post
authors: ["Alicja Gosiewska"]
tags:
- tutorial
---

Posting is really easy. Blog posts are simple Markdown files.


# Files

The `content/post` folder is where blog posts are stored. 
To create a post, add your markdown file to `content/post` directory with the following format:
`yyyy-mm-dd-title.md`.

Where `yyyy` is a year, `mm` is a month, and `dd` is a day, and `md` is the file extension representing the format used in the file. 
For example:
`2020-05-18-how-to-add-post.md`.


# File content

An example of a post file you can find [here](https://github.com/mini-pw/2020L-WB-Blog/blob/master/content/post/2020-05-18-how-to-add-post.md).


A blog post file begins with a front matter which is used to set metadata. For example:

```
---
date: "2020-05-18"
title: How to add a post
authors: ["Alicja Gosiewska"]
tags:
- tutorial
---
```

For more authors, add elements to the list, for example `["Alicja Gosiewska", "Second Author"]`.
Add more tags through the consecutive  punctuation marks.


## Including images

In folder `static` you can create a directory to store images and other necessary files. For example, for file `2020-05-18-how-to-add-post.md` folder should be `static/2020-05-18-how-to-add-post`([See here](https://github.com/mini-pw/2020L-WB-Blog/tree/master/static)).

To include an image `ALICE_all.jpg` from this directory just use:
```
[!A caption](/2020L-WB-Blog/2020-05-18-how-to-add-post/ALICE_all.jpg)
```


![A caption](/2020L-WB-Blog/2020-05-18-how-to-add-post/ALICE_all.jpg)









