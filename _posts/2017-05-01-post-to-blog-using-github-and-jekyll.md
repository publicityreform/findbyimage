---
layout: post
title:  "post to blog using github and jekyll"
date:   2017-05-01 01:52:15 -0700
tags: [Github, jekyll]
categories: [howto]
---

# go to the `_posts` directory in the class github repo [here](https://github.com/publicityreform/findbyimage/tree/master/_posts).

# open any post and click `raw` to see how the post is set up.  

the post is written in [markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet), with a bit of [YAML front matter](https://jekyllrb.com/docs/frontmatter/) that helps the markdown document function as a blog post when it gets displayed on the website. 

you can identify the YAML front matter by the three lines that mark its beginning and end. here's the front matter from this post:

```
---
layout: post
title:  "post to blog using github and jekyll"
date:   2017-05-01 01:52:15 -0700
tags: [Github, jekyll]
categories: [howto]
---
```

it is important that each post have this front matter, specifying: 
- the layout (`post`)
- the title (your choice)
- the date (determines where the post will appear in sequence with other posts, formatted as you see here)
- tags (optional, freeform, anything you want to tag the post with)
- categories (for projects, the category should be set to `projects`... here it is set to `howto` - get it?)

upload any images to the repo's `assets` folder [here](https://github.com/publicityreform/findbyimage/tree/master/assets), and link to them using either:

`![alternate text](assets/images/image-filename.png)` (for images)

embed videos with an iframe

any code, notebooks, or other documents related to your post that you want to share separately can be uploaded to the `assets` directory as well (feel free to create your own subdirectory (this is done when naming a new file, like: `newfolder/myupload.py`), and linked to like so:

- `[link text](assets/newfolder/myupload.py)` (or some variation on this, depending on where the target of your link is!)

# go back to the `_posts` directory and create your post

select `create new file` or `upload files` (if you want to make the .md file somewhere else and upload it)

make sure to give the post a filename formatted with the date first, like: `YYYY-MM-DD-title-of-your-post.md`

make sure to include the YAML front matter as above.

when you are done, click `commit new file` at the bottom. 

if this is your first time contributing to the class repo, you may be asked to create a new fork first. after your first contribution, you should be able to commit directly to the master branch without waiting for the change to be approved 

(we'll see if this works!)



