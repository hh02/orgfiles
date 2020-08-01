# Export org to markdown

## Foreword

Recently, I wang to use org mode to wirte a blog. My blog is on the cnblogs, where has a beautyful skin called "esofar". But the skin only well supports articles in markdown format. The org format is not supported. So I have to convert org files to markdown files. Why don't I use markdown directly? Because I got into the pit of emacs and org is more powerful than markdown. Then, the story starts here.

## Use ox-md (org mode default)

I didn't notice anything unusual of the converted org files at first, but when I publish the articles in cnblogs, I find that the latex fragment was not display. The reason is that delemiter "\$" was convert to "\\(" , but "\\" was a escape character in markdown, it should be "\\\\(". After knowing the reason, it took me an afternonn to find the setting for that, but I didn't find it. So I asked people in the telegram, but nobody can solve this, and he say he use org blog and he don't need to convert org to markdown, but he use pandoc to convert markdown to org. So I wanted to have a try on pandoc.

ps: the error is int the org.el, org-format-latex-options.

## Use ox-pandoc

It has many options, and the latex process is correct. I do not like the setext flavored headlines, it can not well surppot my cnblogs skin's toc function.

## Use ox-hugo

I heard that hugo can directly surppot org, so I wangt to transfer my blog to hugo to avoid converting. Because hugo can Building a hugo blog took me a lot of time. I spent a lot of time on chooseing the skin and deploying to github. Although hugo can directly support org files, it can not surppot very well and it is good at markdown. So I started to use ox-hugo to convert org to markdown. But the markdown converted by ox-hugo has something strange, it is not compatible with the website except hugo. Blogging with hugo is a little troublesome for me, and most importantly, github page is unstable and can not be searched by Baidu. so I gave up hugo.

ps: ox-hugo seems to be ox-md + escape process.

## Use ox-qmd

ox-qmd is based on Markdown back-end(part of GNU Emacs 24) and Github Flavored Markdown back-end. I once tried the latter, it still has no escape process, so I stop using it. The markdown format converted by ox-qmd meets my expectation. I am very satisfied with it. No problems have been found so far.

## Final workflow

1.  Write articles in org mode;
2.  Convert org to markdown;
3.  Publish markdown to cnblogs.

By the way, The inconsistent markdown standard is a headache. ~~Ox-qmd probablly is the package that is most compatible with cnblogs as far as I know.~~ (I found that pandoc is more powerful, see my latter post) But it also has some shortcomings. For example, it will add some html tags to markdown instead of escaping. The readability of the source code will be reduced.

## 2020-8-1 update

I find pandoc is more powerful, and the gfm format is well compatible with cnblogs, I will use org + pandoc + cnblogs to blogging.
