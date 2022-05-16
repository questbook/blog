This repo is used to generate the files that will be served on https://blog.questbook.xyz

# Adding blog posts
## Clone
Clone this repo recursively using : 
```
git clone --recurse-submodules git@github.com:questbook/blog.git
```
## Install hugo
Install Hugo. You can [follow instructions here](https://gohugo.io/getting-started/installing/) 
## Add post
From the root `blog/` run
```
hugo new posts/title-of-your-blog.md
```
## Write your blog
edit the file
```
vim content/posts/title-of-your-blog.md
```
## Undraft your blog
edit `content/posts/title-of-your-blog.md`
replace
`draft: true` with `draft: false`
## Build
in the folder `blog/`
```
hugo
```
## Push
### blog
From `blog/`
```
git add .
git commit -m "added new blog title-of-your-blog"
git push
```
### public
from `public`
```
git add .
git commit -m "added new blog title-of-your-blog"
git push
```
## Done!
After ~2min check https://blog.questbook.xyz
