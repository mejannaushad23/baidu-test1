# 百度SEO针对跨境电商book的Robots.txt配置技巧

对于运营跨境电商book类网站的站长来说，百度SEO 针对跨境电商的book 优化是一项需要精细操作的长期工程。许多站长把精力集中在关键词布局和外链建设上，却忽略了网站根目录下一个看似简单、实则至关重要的文件——Robots.txt。这个文件直接决定了百度蜘蛛能抓取哪些内容、跳过哪些页面，从而影响整站的收录质量和排名表现。本文将深入探讨如何通过科学配置Robots.txt，让百度SEO 针对跨境电商的book 的收录效率与安全性同步提升，帮助你的book站点在百度搜索结果中获得更稳健的流量。

## 理解Robots.txt对百度蜘蛛的特殊意义

在百度SEO 针对跨境电商的book 的实践中，Robots.txt是搜索引擎与网站之间的第一道“沟通协议”。当百度蜘蛛访问你的book站点时，它首先会读取根目录下的Robots.txt文件，根据其中的指令决定哪些URL可以抓取，哪些需要跳过。如果你的配置不当，百度蜘蛛可能被引导至无价值的页面，比如购物车、后台登录、重复的筛选参数链接，从而浪费了宝贵的抓取配额。对于跨境电商book类网站，产品页面、分类页面、博客文章是核心价值内容，而用户评论页、搜索结果页、标签聚合页往往属于低质量或重复内容。因此，合理的Robots.txt配置能让百度蜘蛛集中资源抓取那些能带来排名的页面，这是百度SEO 针对跨境电商的book 的基础保障。

值得注意的是，百度对Robots.txt的解析与Google存在细微差异，例如百度对“Disallow”指令的优先级处理更严格。如果你的book站点面向国际用户，但主要流量来自百度，那么配置时必须优先考虑百度蜘蛛的行为习惯。比如，百度蜘蛛对动态URL的容忍度较低，如果book网站使用了大量参数（如`?sort=price&color=red`），建议在Robots.txt中明确禁止这类URL的抓取。这种针对性调整，正是百度SEO 针对跨境电商的book 区别于通用SEO的核心所在。

## 禁止抓取无价值的重复内容与系统路径

跨境电商book类网站通常包含大量系统自动生成的页面，这些页面对于用户和搜索引擎来说几乎没有独立价值。例如，用户登录页面、购物车页面、订单查询页面、支付回调页面等，它们既不需要被索引，也不应该被蜘蛛抓取。在百度SEO 针对跨境电商的book 的优化中，优先屏蔽这些路径能显著提升蜘蛛效率。常见的需要禁止的路径包括：`/cart/`、`/login/`、`/register/`、`/checkout/`、`/my-account/`、`/admin/`等。

此外，许多book网站使用了多语言或多货币功能，导致同一本书在不同参数下生成多个URL。例如，`/book/123?lang=en` 和 `/book/123?lang=zh` 可能内容相同，只是语言标记不同。这类重复URL会稀释权重，导致百度无法确定哪个版本是首选。在Robots.txt中，你可以通过Disallow指令禁止所有带参数的语言切换链接，同时保留规范的静态URL。例如：

```
User-agent: Baiduspider
Disallow: /cart/
Disallow: /login/
Disallow: /my-account/
Disallow: /*?lang=
Disallow: /*?currency=
```

这种配置让百度蜘蛛只抓取干净的、无参数的核心页面，从而让百度SEO 针对跨境电商的book 的收录结果更加聚焦。需要注意的是，不要过度禁止——如果某些参数页面确实有独立价值（如按分类筛选的书籍列表），则应保留并配合Canonical标签处理。

## 合理利用Allow指令优先抓取核心内容

Robots.txt并非只能用来“禁止”，它同样可以配合Allow指令来引导蜘蛛优先抓取最重要的内容。在百度SEO 针对跨境电商的book 的优化中，你可以先禁止整个目录，再单独允许某个子目录或特定页面，从而实现精细控制。例如，假设你的book站点有一个`/product/`目录存放所有书籍详情页，但其中包含了大量无用的临时页面（如`/product/temp/`），你可以这样写：

```
User-agent: Baiduspider
Disallow: /product/
Allow: /product/books/
Allow: /product/category/
```

这种写法告诉百度蜘蛛：“整个/product/目录默认不抓取，但/product/books/和/product/category/下的内容可以访问。”这种方式非常适合大型跨境电商book网站，它们通常有成千上万的产品页面，但只有一部分是当前主推或高转化率的。通过Allow指令，你可以将蜘蛛的抓取预算集中在核心书籍页面上，从而加快新书的收录速度。这是百度SEO 针对跨境电商的book 中一种高级但非常有效的策略。

## 处理分页与筛选页面的抓取策略

跨境电商book站点往往有大量的分页和筛选结果页，例如“按出版社筛选”、“按价格区间筛选”等。这类页面内容高度相似，如果全部被百度收录，会造成严重的重复内容问题。在百度SEO 针对跨境电商的book 的配置中，推荐的做法是：只允许第一页被抓取，后续分页通过Disallow禁止。例如：

```
User-agent: Baiduspider
Disallow: /books/page/2
Disallow: /books/page/3
...
```

当然，更简洁的做法是使用通配符禁止所有分页参数，前提是你的URL结构规范。例如，如果分页URL格式为`/books?page=2`，则可以用`Disallow: /*?page=`来统一禁止。同时，对于筛选参数，如`?filter=author`或`?sort=price`，也建议统一禁止。这样，百度蜘蛛只会抓取每个分类或书籍的主页面，而不会陷入无限的参数组合中。这种策略能大幅提升百度SEO 针对跨境电商的book 的收录质量，避免低质量页面稀释权重。

## 注意Robots.txt的语法细节与测试方法

配置Robots.txt时，语法错误可能导致整个文件失效，甚至意外屏蔽所有内容。对于百度SEO 针对跨境电商的book 的优化，有几个关键点必须牢记：第一，每个指令独占一行，不得合并；第二，User-agent必须单独一行，且区分大小写（Baiduspider是标准写法）；第三，路径以斜杠开头，且区分大小写；第四，注释用`#`开头，但建议尽量减少注释，以免被误解析。另外，百度蜘蛛支持通配符`*`和`$`结尾符，但使用前最好在百度资源平台中验证。

测试是必不可少的一步。你可以使用百度搜索资源平台的“Robots.txt工具”或直接在浏览器中访问`https://你的域名/robots.txt`来检查文件是否可访问。更严谨的做法是，在修改后观察百度站长后台的“抓取异常”数据，看是否有核心页面被错误禁止。例如，有些站长不小心禁用了`/`，导致整个网站无法被抓取，这是致命错误。因此，每次修改后，建议用百度蜘蛛模拟工具抓取几个典型页面（如首页、分类页、书籍详情页），确保它们都能被正常访问。这是保障百度SEO 针对跨境电商的book 持续有效的基础。

## 动态更新Robots.txt以应对网站变化

跨境电商book站点并非一成不变，产品会下架、分类会调整、新功能会上线。因此，Robots.txt也应作为一个动态文件定期审视。例如，当你的book网站上线了一个新的博客板块，用于发布书籍推荐和行业资讯，那么这些博客页面应该被允许抓取，因为它们能带来长尾流量。相反，如果某个旧的促销活动页面已经失效，则应将其加入Disallow列表。在百度SEO 针对跨境电商的book 的长期运维中，每季度或每次较大改版后，都应重新评估Robots.txt的配置是否合理。

此外，如果你的book站点使用了CDN或反向代理，确保Robots.txt文件在所有节点上一致，否则不同地区的蜘蛛可能看到不同内容。同时，注意文件大小——百度官方建议Robots.txt不超过500KB，但实际中多数站点远小于此。对于大型跨境电商book网站，如果文件过于复杂，可以考虑将部分规则移至更细粒度的元标签（如noindex）中，而非全部依赖Robots.txt。这样既能保持灵活性，又不会让Robots.txt变得臃肿难维护。

## 总结

Robots.txt是百度SEO 针对跨境电商的book 优化的一个关键支点，它虽小，却直接决定了蜘蛛的抓取方向与效率。通过禁止无价值的系统路径、重复的分页与筛选页面，同时利用Allow指令突出核心书籍内容，你可以让百度蜘蛛的每一次爬行都更有价值。记住，配置完成后务必测试并持续监控，根据网站变化动态调整。一个精细打磨过的Robots.txt文件，能帮助你的跨境电商book站点在百度搜索结果中抢占先机，让优质内容更快、更稳地展现在目标用户面前。希望本文的技巧能为你带来实质性的收录提升与流量增长。

## 相关链接

- [http://www.blog.kjbje.cn/Article/details/101269.sHtML](http://www.blog.kjbje.cn/Article/details/101269.sHtML)
- [http://www.blog.kjbje.cn/Article/details/686692.sHtML](http://www.blog.kjbje.cn/Article/details/686692.sHtML)
- [http://www.blog.kjbje.cn/Article/details/154646.sHtML](http://www.blog.kjbje.cn/Article/details/154646.sHtML)
- [http://www.blog.kjbje.cn/Article/details/860090.sHtML](http://www.blog.kjbje.cn/Article/details/860090.sHtML)
- [http://www.blog.kjbje.cn/Article/details/004820.sHtML](http://www.blog.kjbje.cn/Article/details/004820.sHtML)
- [http://www.blog.kjbje.cn/Article/details/017432.sHtML](http://www.blog.kjbje.cn/Article/details/017432.sHtML)
- [http://www.blog.kjbje.cn/Article/details/892197.sHtML](http://www.blog.kjbje.cn/Article/details/892197.sHtML)
- [http://www.blog.kjbje.cn/Article/details/738683.sHtML](http://www.blog.kjbje.cn/Article/details/738683.sHtML)
- [http://www.blog.kjbje.cn/Article/details/489430.sHtML](http://www.blog.kjbje.cn/Article/details/489430.sHtML)
- [http://www.blog.kjbje.cn/Article/details/354643.sHtML](http://www.blog.kjbje.cn/Article/details/354643.sHtML)
- [http://www.blog.kjbje.cn/Article/details/918916.sHtML](http://www.blog.kjbje.cn/Article/details/918916.sHtML)
- [http://www.blog.kjbje.cn/Article/details/188658.sHtML](http://www.blog.kjbje.cn/Article/details/188658.sHtML)
- [http://www.blog.kjbje.cn/Article/details/762702.sHtML](http://www.blog.kjbje.cn/Article/details/762702.sHtML)
- [http://www.blog.kjbje.cn/Article/details/023235.sHtML](http://www.blog.kjbje.cn/Article/details/023235.sHtML)
- [http://www.blog.kjbje.cn/Article/details/621863.sHtML](http://www.blog.kjbje.cn/Article/details/621863.sHtML)
- [http://www.blog.kjbje.cn/Article/details/201135.sHtML](http://www.blog.kjbje.cn/Article/details/201135.sHtML)
- [http://www.blog.kjbje.cn/Article/details/011945.sHtML](http://www.blog.kjbje.cn/Article/details/011945.sHtML)
- [http://www.blog.kjbje.cn/Article/details/120482.sHtML](http://www.blog.kjbje.cn/Article/details/120482.sHtML)
- [http://www.blog.kjbje.cn/Article/details/771705.sHtML](http://www.blog.kjbje.cn/Article/details/771705.sHtML)
- [http://www.blog.kjbje.cn/Article/details/863605.sHtML](http://www.blog.kjbje.cn/Article/details/863605.sHtML)
- [http://www.blog.kjbje.cn/Article/details/016527.sHtML](http://www.blog.kjbje.cn/Article/details/016527.sHtML)
- [http://www.blog.kjbje.cn/Article/details/398987.sHtML](http://www.blog.kjbje.cn/Article/details/398987.sHtML)
- [http://www.blog.kjbje.cn/Article/details/228977.sHtML](http://www.blog.kjbje.cn/Article/details/228977.sHtML)
- [http://www.blog.kjbje.cn/Article/details/620359.sHtML](http://www.blog.kjbje.cn/Article/details/620359.sHtML)
- [http://www.blog.kjbje.cn/Article/details/292975.sHtML](http://www.blog.kjbje.cn/Article/details/292975.sHtML)
- [http://www.blog.kjbje.cn/Article/details/304968.sHtML](http://www.blog.kjbje.cn/Article/details/304968.sHtML)
- [http://www.blog.kjbje.cn/Article/details/163158.sHtML](http://www.blog.kjbje.cn/Article/details/163158.sHtML)
- [http://www.blog.kjbje.cn/Article/details/363198.sHtML](http://www.blog.kjbje.cn/Article/details/363198.sHtML)
- [http://www.blog.kjbje.cn/Article/details/543615.sHtML](http://www.blog.kjbje.cn/Article/details/543615.sHtML)
- [http://www.blog.kjbje.cn/Article/details/666597.sHtML](http://www.blog.kjbje.cn/Article/details/666597.sHtML)
- [http://www.blog.kjbje.cn/Article/details/952512.sHtML](http://www.blog.kjbje.cn/Article/details/952512.sHtML)
- [http://www.blog.kjbje.cn/Article/details/586890.sHtML](http://www.blog.kjbje.cn/Article/details/586890.sHtML)
- [http://www.blog.kjbje.cn/Article/details/655585.sHtML](http://www.blog.kjbje.cn/Article/details/655585.sHtML)
- [http://www.blog.kjbje.cn/Article/details/200103.sHtML](http://www.blog.kjbje.cn/Article/details/200103.sHtML)
- [http://www.blog.kjbje.cn/Article/details/216214.sHtML](http://www.blog.kjbje.cn/Article/details/216214.sHtML)
- [http://www.blog.kjbje.cn/Article/details/861765.sHtML](http://www.blog.kjbje.cn/Article/details/861765.sHtML)
- [http://www.blog.kjbje.cn/Article/details/776990.sHtML](http://www.blog.kjbje.cn/Article/details/776990.sHtML)
- [http://www.blog.kjbje.cn/Article/details/852212.sHtML](http://www.blog.kjbje.cn/Article/details/852212.sHtML)
- [http://www.blog.kjbje.cn/Article/details/548221.sHtML](http://www.blog.kjbje.cn/Article/details/548221.sHtML)
- [http://www.blog.kjbje.cn/Article/details/677694.sHtML](http://www.blog.kjbje.cn/Article/details/677694.sHtML)
- [http://www.blog.kjbje.cn/Article/details/814501.sHtML](http://www.blog.kjbje.cn/Article/details/814501.sHtML)
- [http://www.blog.kjbje.cn/Article/details/002361.sHtML](http://www.blog.kjbje.cn/Article/details/002361.sHtML)
- [http://www.blog.kjbje.cn/Article/details/820816.sHtML](http://www.blog.kjbje.cn/Article/details/820816.sHtML)
- [http://www.blog.kjbje.cn/Article/details/169341.sHtML](http://www.blog.kjbje.cn/Article/details/169341.sHtML)
- [http://www.blog.kjbje.cn/Article/details/035165.sHtML](http://www.blog.kjbje.cn/Article/details/035165.sHtML)
- [http://www.blog.kjbje.cn/Article/details/700706.sHtML](http://www.blog.kjbje.cn/Article/details/700706.sHtML)
- [http://www.blog.kjbje.cn/Article/details/317416.sHtML](http://www.blog.kjbje.cn/Article/details/317416.sHtML)
- [http://www.blog.kjbje.cn/Article/details/700496.sHtML](http://www.blog.kjbje.cn/Article/details/700496.sHtML)
- [http://www.blog.kjbje.cn/Article/details/686771.sHtML](http://www.blog.kjbje.cn/Article/details/686771.sHtML)
- [http://www.blog.kjbje.cn/Article/details/760937.sHtML](http://www.blog.kjbje.cn/Article/details/760937.sHtML)
- [http://www.blog.kjbje.cn/Article/details/039078.sHtML](http://www.blog.kjbje.cn/Article/details/039078.sHtML)
- [http://www.blog.kjbje.cn/Article/details/590469.sHtML](http://www.blog.kjbje.cn/Article/details/590469.sHtML)
- [http://www.blog.kjbje.cn/Article/details/997086.sHtML](http://www.blog.kjbje.cn/Article/details/997086.sHtML)
- [http://www.blog.kjbje.cn/Article/details/824857.sHtML](http://www.blog.kjbje.cn/Article/details/824857.sHtML)
- [http://www.blog.kjbje.cn/Article/details/171200.sHtML](http://www.blog.kjbje.cn/Article/details/171200.sHtML)
- [http://www.blog.kjbje.cn/Article/details/961192.sHtML](http://www.blog.kjbje.cn/Article/details/961192.sHtML)
- [http://www.blog.kjbje.cn/Article/details/350988.sHtML](http://www.blog.kjbje.cn/Article/details/350988.sHtML)
- [http://www.blog.kjbje.cn/Article/details/280081.sHtML](http://www.blog.kjbje.cn/Article/details/280081.sHtML)
- [http://www.blog.kjbje.cn/Article/details/010703.sHtML](http://www.blog.kjbje.cn/Article/details/010703.sHtML)
- [http://www.blog.kjbje.cn/Article/details/017529.sHtML](http://www.blog.kjbje.cn/Article/details/017529.sHtML)
- [http://www.blog.kjbje.cn/Article/details/719065.sHtML](http://www.blog.kjbje.cn/Article/details/719065.sHtML)
- [http://www.blog.kjbje.cn/Article/details/823485.sHtML](http://www.blog.kjbje.cn/Article/details/823485.sHtML)
- [http://www.blog.kjbje.cn/Article/details/121496.sHtML](http://www.blog.kjbje.cn/Article/details/121496.sHtML)
- [http://www.blog.kjbje.cn/Article/details/511483.sHtML](http://www.blog.kjbje.cn/Article/details/511483.sHtML)
- [http://www.blog.kjbje.cn/Article/details/162213.sHtML](http://www.blog.kjbje.cn/Article/details/162213.sHtML)
- [http://www.blog.kjbje.cn/Article/details/967096.sHtML](http://www.blog.kjbje.cn/Article/details/967096.sHtML)
- [http://www.blog.kjbje.cn/Article/details/563384.sHtML](http://www.blog.kjbje.cn/Article/details/563384.sHtML)
- [http://www.blog.kjbje.cn/Article/details/372141.sHtML](http://www.blog.kjbje.cn/Article/details/372141.sHtML)
- [http://www.blog.kjbje.cn/Article/details/927969.sHtML](http://www.blog.kjbje.cn/Article/details/927969.sHtML)
- [http://www.blog.kjbje.cn/Article/details/756268.sHtML](http://www.blog.kjbje.cn/Article/details/756268.sHtML)
- [http://www.blog.kjbje.cn/Article/details/226449.sHtML](http://www.blog.kjbje.cn/Article/details/226449.sHtML)
- [http://www.blog.kjbje.cn/Article/details/286861.sHtML](http://www.blog.kjbje.cn/Article/details/286861.sHtML)
- [http://www.blog.kjbje.cn/Article/details/319555.sHtML](http://www.blog.kjbje.cn/Article/details/319555.sHtML)
- [http://www.blog.kjbje.cn/Article/details/627488.sHtML](http://www.blog.kjbje.cn/Article/details/627488.sHtML)
- [http://www.blog.kjbje.cn/Article/details/684908.sHtML](http://www.blog.kjbje.cn/Article/details/684908.sHtML)
- [http://www.blog.kjbje.cn/Article/details/604813.sHtML](http://www.blog.kjbje.cn/Article/details/604813.sHtML)
- [http://www.blog.kjbje.cn/Article/details/628369.sHtML](http://www.blog.kjbje.cn/Article/details/628369.sHtML)
- [http://www.blog.kjbje.cn/Article/details/085951.sHtML](http://www.blog.kjbje.cn/Article/details/085951.sHtML)
- [http://www.blog.kjbje.cn/Article/details/658303.sHtML](http://www.blog.kjbje.cn/Article/details/658303.sHtML)
- [http://www.blog.kjbje.cn/Article/details/278063.sHtML](http://www.blog.kjbje.cn/Article/details/278063.sHtML)
- [http://www.blog.kjbje.cn/Article/details/255831.sHtML](http://www.blog.kjbje.cn/Article/details/255831.sHtML)
- [http://www.blog.kjbje.cn/Article/details/286044.sHtML](http://www.blog.kjbje.cn/Article/details/286044.sHtML)
- [http://www.blog.kjbje.cn/Article/details/528559.sHtML](http://www.blog.kjbje.cn/Article/details/528559.sHtML)
- [http://www.blog.kjbje.cn/Article/details/228434.sHtML](http://www.blog.kjbje.cn/Article/details/228434.sHtML)
- [http://www.blog.kjbje.cn/Article/details/922705.sHtML](http://www.blog.kjbje.cn/Article/details/922705.sHtML)
- [http://www.blog.kjbje.cn/Article/details/843742.sHtML](http://www.blog.kjbje.cn/Article/details/843742.sHtML)
- [http://www.blog.kjbje.cn/Article/details/668843.sHtML](http://www.blog.kjbje.cn/Article/details/668843.sHtML)
- [http://www.blog.kjbje.cn/Article/details/783476.sHtML](http://www.blog.kjbje.cn/Article/details/783476.sHtML)
- [http://www.blog.kjbje.cn/Article/details/884948.sHtML](http://www.blog.kjbje.cn/Article/details/884948.sHtML)
- [http://www.blog.kjbje.cn/Article/details/624783.sHtML](http://www.blog.kjbje.cn/Article/details/624783.sHtML)
- [http://www.blog.kjbje.cn/Article/details/149069.sHtML](http://www.blog.kjbje.cn/Article/details/149069.sHtML)
- [http://www.blog.kjbje.cn/Article/details/547941.sHtML](http://www.blog.kjbje.cn/Article/details/547941.sHtML)
- [http://www.blog.kjbje.cn/Article/details/772337.sHtML](http://www.blog.kjbje.cn/Article/details/772337.sHtML)
- [http://www.blog.kjbje.cn/Article/details/023760.sHtML](http://www.blog.kjbje.cn/Article/details/023760.sHtML)
- [http://www.blog.kjbje.cn/Article/details/337160.sHtML](http://www.blog.kjbje.cn/Article/details/337160.sHtML)
- [http://www.blog.kjbje.cn/Article/details/356155.sHtML](http://www.blog.kjbje.cn/Article/details/356155.sHtML)
- [http://www.blog.kjbje.cn/Article/details/022465.sHtML](http://www.blog.kjbje.cn/Article/details/022465.sHtML)
- [http://www.blog.kjbje.cn/Article/details/173940.sHtML](http://www.blog.kjbje.cn/Article/details/173940.sHtML)
- [http://www.blog.kjbje.cn/Article/details/114678.sHtML](http://www.blog.kjbje.cn/Article/details/114678.sHtML)
- [http://www.blog.kjbje.cn/Article/details/689041.sHtML](http://www.blog.kjbje.cn/Article/details/689041.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/460230.sHtML](http://www.blog.cvbhg.cn/Article/details/460230.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/003164.sHtML](http://www.blog.cvbhg.cn/Article/details/003164.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/978587.sHtML](http://www.blog.cvbhg.cn/Article/details/978587.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/870387.sHtML](http://www.blog.cvbhg.cn/Article/details/870387.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/863892.sHtML](http://www.blog.cvbhg.cn/Article/details/863892.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/297583.sHtML](http://www.blog.cvbhg.cn/Article/details/297583.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/013834.sHtML](http://www.blog.cvbhg.cn/Article/details/013834.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/430947.sHtML](http://www.blog.cvbhg.cn/Article/details/430947.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/700667.sHtML](http://www.blog.cvbhg.cn/Article/details/700667.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/192358.sHtML](http://www.blog.cvbhg.cn/Article/details/192358.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/785066.sHtML](http://www.blog.cvbhg.cn/Article/details/785066.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/803859.sHtML](http://www.blog.cvbhg.cn/Article/details/803859.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/077216.sHtML](http://www.blog.cvbhg.cn/Article/details/077216.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/985838.sHtML](http://www.blog.cvbhg.cn/Article/details/985838.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/586607.sHtML](http://www.blog.cvbhg.cn/Article/details/586607.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/170618.sHtML](http://www.blog.cvbhg.cn/Article/details/170618.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/644025.sHtML](http://www.blog.cvbhg.cn/Article/details/644025.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/120031.sHtML](http://www.blog.cvbhg.cn/Article/details/120031.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/206847.sHtML](http://www.blog.cvbhg.cn/Article/details/206847.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/495226.sHtML](http://www.blog.cvbhg.cn/Article/details/495226.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/827506.sHtML](http://www.blog.cvbhg.cn/Article/details/827506.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/950999.sHtML](http://www.blog.cvbhg.cn/Article/details/950999.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/125156.sHtML](http://www.blog.cvbhg.cn/Article/details/125156.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/226633.sHtML](http://www.blog.cvbhg.cn/Article/details/226633.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/610598.sHtML](http://www.blog.cvbhg.cn/Article/details/610598.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/300741.sHtML](http://www.blog.cvbhg.cn/Article/details/300741.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/836511.sHtML](http://www.blog.cvbhg.cn/Article/details/836511.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/555207.sHtML](http://www.blog.cvbhg.cn/Article/details/555207.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/862042.sHtML](http://www.blog.cvbhg.cn/Article/details/862042.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/608749.sHtML](http://www.blog.cvbhg.cn/Article/details/608749.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/457543.sHtML](http://www.blog.cvbhg.cn/Article/details/457543.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/008729.sHtML](http://www.blog.cvbhg.cn/Article/details/008729.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/290816.sHtML](http://www.blog.cvbhg.cn/Article/details/290816.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/372246.sHtML](http://www.blog.cvbhg.cn/Article/details/372246.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/808437.sHtML](http://www.blog.cvbhg.cn/Article/details/808437.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/682246.sHtML](http://www.blog.cvbhg.cn/Article/details/682246.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/638591.sHtML](http://www.blog.cvbhg.cn/Article/details/638591.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/216199.sHtML](http://www.blog.cvbhg.cn/Article/details/216199.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/178322.sHtML](http://www.blog.cvbhg.cn/Article/details/178322.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/926410.sHtML](http://www.blog.cvbhg.cn/Article/details/926410.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/462474.sHtML](http://www.blog.cvbhg.cn/Article/details/462474.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/115330.sHtML](http://www.blog.cvbhg.cn/Article/details/115330.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/816999.sHtML](http://www.blog.cvbhg.cn/Article/details/816999.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/051889.sHtML](http://www.blog.cvbhg.cn/Article/details/051889.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/378884.sHtML](http://www.blog.cvbhg.cn/Article/details/378884.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/876229.sHtML](http://www.blog.cvbhg.cn/Article/details/876229.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/406313.sHtML](http://www.blog.cvbhg.cn/Article/details/406313.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/638095.sHtML](http://www.blog.cvbhg.cn/Article/details/638095.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/712543.sHtML](http://www.blog.cvbhg.cn/Article/details/712543.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/372716.sHtML](http://www.blog.cvbhg.cn/Article/details/372716.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/323081.sHtML](http://www.blog.cvbhg.cn/Article/details/323081.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/372416.sHtML](http://www.blog.cvbhg.cn/Article/details/372416.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/327232.sHtML](http://www.blog.cvbhg.cn/Article/details/327232.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/498587.sHtML](http://www.blog.cvbhg.cn/Article/details/498587.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/952260.sHtML](http://www.blog.cvbhg.cn/Article/details/952260.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/068887.sHtML](http://www.blog.cvbhg.cn/Article/details/068887.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/504933.sHtML](http://www.blog.cvbhg.cn/Article/details/504933.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/405272.sHtML](http://www.blog.cvbhg.cn/Article/details/405272.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/861401.sHtML](http://www.blog.cvbhg.cn/Article/details/861401.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/298699.sHtML](http://www.blog.cvbhg.cn/Article/details/298699.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/149858.sHtML](http://www.blog.cvbhg.cn/Article/details/149858.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/529199.sHtML](http://www.blog.cvbhg.cn/Article/details/529199.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/116560.sHtML](http://www.blog.cvbhg.cn/Article/details/116560.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/324740.sHtML](http://www.blog.cvbhg.cn/Article/details/324740.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/915999.sHtML](http://www.blog.cvbhg.cn/Article/details/915999.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/072579.sHtML](http://www.blog.cvbhg.cn/Article/details/072579.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/432425.sHtML](http://www.blog.cvbhg.cn/Article/details/432425.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/091430.sHtML](http://www.blog.cvbhg.cn/Article/details/091430.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/189753.sHtML](http://www.blog.cvbhg.cn/Article/details/189753.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/297233.sHtML](http://www.blog.cvbhg.cn/Article/details/297233.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/994625.sHtML](http://www.blog.cvbhg.cn/Article/details/994625.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/865159.sHtML](http://www.blog.cvbhg.cn/Article/details/865159.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/836444.sHtML](http://www.blog.cvbhg.cn/Article/details/836444.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/090204.sHtML](http://www.blog.cvbhg.cn/Article/details/090204.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/185676.sHtML](http://www.blog.cvbhg.cn/Article/details/185676.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/997589.sHtML](http://www.blog.cvbhg.cn/Article/details/997589.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/407923.sHtML](http://www.blog.cvbhg.cn/Article/details/407923.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/290890.sHtML](http://www.blog.cvbhg.cn/Article/details/290890.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/897956.sHtML](http://www.blog.cvbhg.cn/Article/details/897956.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/190352.sHtML](http://www.blog.cvbhg.cn/Article/details/190352.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/266328.sHtML](http://www.blog.cvbhg.cn/Article/details/266328.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/913604.sHtML](http://www.blog.cvbhg.cn/Article/details/913604.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/522770.sHtML](http://www.blog.cvbhg.cn/Article/details/522770.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/340433.sHtML](http://www.blog.cvbhg.cn/Article/details/340433.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/271470.sHtML](http://www.blog.cvbhg.cn/Article/details/271470.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/047119.sHtML](http://www.blog.cvbhg.cn/Article/details/047119.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/060774.sHtML](http://www.blog.cvbhg.cn/Article/details/060774.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/751108.sHtML](http://www.blog.cvbhg.cn/Article/details/751108.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/328720.sHtML](http://www.blog.cvbhg.cn/Article/details/328720.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/453828.sHtML](http://www.blog.cvbhg.cn/Article/details/453828.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/042515.sHtML](http://www.blog.cvbhg.cn/Article/details/042515.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/200740.sHtML](http://www.blog.cvbhg.cn/Article/details/200740.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/071276.sHtML](http://www.blog.cvbhg.cn/Article/details/071276.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/481053.sHtML](http://www.blog.cvbhg.cn/Article/details/481053.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/137702.sHtML](http://www.blog.cvbhg.cn/Article/details/137702.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/176511.sHtML](http://www.blog.cvbhg.cn/Article/details/176511.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/230553.sHtML](http://www.blog.cvbhg.cn/Article/details/230553.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/624658.sHtML](http://www.blog.cvbhg.cn/Article/details/624658.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/663934.sHtML](http://www.blog.cvbhg.cn/Article/details/663934.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/305396.sHtML](http://www.blog.cvbhg.cn/Article/details/305396.sHtML)
