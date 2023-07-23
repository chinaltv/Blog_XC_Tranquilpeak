# readme

该文档用于解释网站上制作的一切修订（基于宁静峰主题），并附带blogdown项目的简要笔记。2022年做的修改不再记录。

&nbsp;

* ~/config.yaml 用于决定网站风格和网站结构。与content联动。

在config.yaml里，我：

1. 删除了无用的分享链接，修订分享到推特和脸书的网站链接，并新加分享到微博。预留一个接口分享到微信，但是还没做。
2. 尝试修复Disqus问题。见：https://stackoverflow.com/questions/44098635/disqus-plugin-social-urls-dont-load-in-site-generated-using-r-blogdown和https://github.com/rstudio/blogdown/issues/52。基本而言，我就是尝试blogdown::build_site()后再blogdown::serve_site()，并且在config.yaml里加入了base_url（基于我买的域名）

&nbsp;

* ~/public 用于发布网站。例如，netlify会解析public文件夹的所有信息并将其生成网站。本部分由blogdown::serve_site()构建，不需要你操作。
* ~/resources 未知

&nbsp;

* ~/Netlify.toml 用于决定Netlify的配置。不需要你操作。
* ~/Index.rmd 用于配置blogdown包，不要动。
* ~/.Rhistory/.Rdata/.Rprofile三连 R文件，没啥用，不用管

&nbsp;

* ~/content/post用于存放你的博文。任何对于内容的修订都应在这个文件夹完成。
* ~/static 静态资源，用于你发布的东西的静态资源，例如图片

&nbsp;

* ~/theme/hugo-tranquilpeak-theme

基本主题资源。在2022年我好像做了点修改，但是忘了改了什么了。

&nbsp;

* ~/layout 主要用于顶替theme/hugo-tranquilpeak-theme/layouts主题中的原始模板。可以看：https://bookdown.org/yihui/blogdown/custom-layouts.html

我暂时没有创建layout文件夹。写在这里的原因是我曾经尝试加入utterances作为第三方评论区（参照：https://www.r-bloggers.com/2019/10/goodbye-disqus-hello-utterances/）。后面发现utterances需要github账户登陆才能评论，这不符合我的个人博客风格。
