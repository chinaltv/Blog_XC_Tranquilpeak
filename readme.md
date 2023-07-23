# readme

该文档用于解释网站上制作的一切修订（基于宁静峰主题），并附带blogdown项目的简要笔记。2022年做的修改不再记录。

&nbsp;

* ~/config.yaml 用于决定网站风格和网站结构。与content联动。

在config.yaml里，我：

1. 删除了无用的分享链接，修订分享到推特和脸书的网站链接，并新加分享到微博。我只是修改了config.yaml文件，并没有在模板文件share-options.html里面改动h5（其工作原理是将href这个变量替换到前面config.yaml的%s）。出于我的能力问题，我曾尝试修改href使其加入固定字符串“我的域名”，但失败了。预留一个接口分享到微信，但是还没做。
2. 尝试修复Disqus问题。见：https://stackoverflow.com/questions/44098635/disqus-plugin-social-urls-dont-load-in-site-generated-using-r-blogdown和https://github.com/rstudio/blogdown/issues/52。基本而言，我就是尝试blogdown::build_site()后再blogdown::serve_site()。记得将baseURL改成https://我的域名。不要写成http://，会冲突。

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

基本主题资源。在2022年我好像做了点修改，但是忘了改了什么了。（应该是一些颜色、侧边栏之类的设置，通过customJS完成）

&nbsp;

* ~/layout 主要用于顶替theme/hugo-tranquilpeak-theme/layouts主题中的原始模板。可以看：https://bookdown.org/yihui/blogdown/custom-layouts.html

&nbsp;

2023.07.24
我曾经尝试加入utterances作为第三方评论区（参照：https://www.r-bloggers.com/2019/10/goodbye-disqus-hello-utterances/）。后面发现utterances需要github账户登陆才能评论，这不符合我的个人博客风格。后面加入layout原因是因为我需要益辉大神的disqus模板来让我的disqus正常启动（但是我不太清楚起作用的究竟是baseURL还是这一个html文件。在实际使用中我发现disqus仍然需要登录，所以现在只是放了一个好看的“评论区”在我的博客里，实质上没有比utterances或者Giscus更好，除了利好非翻墙用户不用注册Github（考虑到我这个博客的性质，我觉得没啥问题）。并且，解决这些问题耗费了我和chatGPT接近周末一天的时间，让我非常恼火（剩下一半时间在看弹丸论破雾切）。

在后续我可能会考虑删掉disqus（这应该是一个麻烦的要死的事情），并全面替换成Isso或者Cactus。考虑到他们又匿名又美观，还不用注册，我希望能在今年完成，但谁知道呢，最近忙的要死，再说吧。
