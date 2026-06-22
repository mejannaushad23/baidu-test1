# 百度SEO针对跨境电商book的nofollow标签使用场景：精准控权与流量优化指南

在跨境电商独立站的运营中，book类产品（如电子书、纸质书、教育类书籍、期刊订阅等）往往面临内容体量大、站内链接复杂、用户路径多元的挑战。许多站长在优化「百度SEO 针对跨境电商的book」时，容易陷入一个误区：认为所有内链和外链的价值都是正向的，从而不加区分地开放所有链接的权重传递。事实上，**合理使用nofollow标签，恰恰是控制权重流动、保护核心页面、提升收录效率的关键手段**。本文将从实战角度，拆解在book类跨境电商场景下，哪些链接必须加nofollow，以及如何在不损伤用户体验的前提下，为百度SEO注入精准的控制力。

## 一、为什么book类跨境电商特别需要关注nofollow标签？

book类电商站点的结构有其特殊性：一个典型的产品页可能包含作者介绍、目录预览、章节试读、用户书评、相关推荐、出版社链接等数十个链接。如果全部不加nofollow，百度蜘蛛会陷入“链接迷宫”，导致两个严重后果：一是权重被大量低价值链接稀释，核心产品页无法获得足够的抓取资源；二是高权重页面被非核心链接“带走”，影响整站的主题相关性。

举个例子，某家销售英文原版教材的跨境电商站，在产品详情页底部放置了“同类书籍推荐”模块，每个推荐链接都指向其他产品页。如果这几十个推荐链接全部传递权重，那么百度蜘蛛可能花费大量时间在推荐模块中循环爬取，反而忽略了最重要的购买入口和内容详情。**针对跨境电商的book，百度SEO的核心逻辑是“集中优势兵力打歼灭战”** ——让权重优先流向能产生转化和排名的页面，而nofollow就是实现这一目标的“阀门”。

## 二、nofollow在book类站点中的三大核心使用场景

### 1. 用户生成内容（UGC）中的外部链接：必须加nofollow

book类跨境电商站通常设有书评区、读者论坛或问答社区。用户在这些区域发布的评论中，常常会附带个人博客、社交媒体链接，甚至直接推广竞品书籍。对于这类外链，**百度SEO针对跨境电商的book** 的优化策略是：一律添加nofollow。

原因很简单：你无法控制UGC链接的质量。一旦某个用户留下的链接被判定为低质量或垃圾外链，百度可能会连带惩罚你的网站。更务实的做法是，在编辑器层面强制对所有用户提交的链接添加`rel="nofollow"`，同时保留链接的点击功能（不影响用户体验）。这样既维护了社区的互动性，又避免了权重流失和风险传递。需要注意的是，某些SEO插件会默认对第三方作者链接加nofollow，但在百度环境中，建议再检查一下是否覆盖了“回复中的链接”和“签名档链接”。

### 2. 辅助功能页面与重复内容页面：用nofollow避免权重分散

book类站点中充斥着大量“功能型页面”，比如：购物车、结算页、用户登录、订单查询、帮助中心、运费计算器等。这些页面对用户有用，但对搜索引擎排名几乎没有贡献——用户不会通过搜索“购物车”来找到你的书。更关键的是，百度蜘蛛如果频繁爬取这些动态URL（如`/cart?user=123`），会占用宝贵的抓取预算。

建议对这些页面使用`<meta name="robots" content="noindex, nofollow">`（禁止索引且禁止跟踪链接），或者在页面内的所有导航链接上加nofollow。尤其是结算流程中的“继续购物”链接，它指向的产品页如果被nofollow，反而有助于集中权重。此外，如果book站点使用了翻页筛选功能（如按出版社、出版年份、价格区间筛选），这些筛选页的内容通常与已有分类页高度重复，建议在筛选结果页的根链接上加nofollow，避免百度将重复内容误判为低质量。

### 3. 付费推广与联盟链接：必须用nofollow标记

许多book类跨境电商站会参与亚马逊联盟、出版社合作推广，或者在自己的站内投放广告。对于这些“带参数”的追踪链接（如`/redirect?url=xxx&affid=123`），以及付费推广的锚文本链接，**百度SEO针对跨境电商的book** 的黄金法则是：所有付费或广告性质的链接，一律加nofollow。

百度站长平台明确将“付费链接未声明”视为违规行为，可能触发惩罚。更隐蔽的风险在于：如果这些推广链接指向的页面（如第三方书店）质量低劣，百度可能会认为你的站是在“导出垃圾链接”，从而降低整站权重。正确的做法是，在广告位代码中直接写入`<a href="..." rel="nofollow" target="_blank">`，同时在网站的robots.txt中禁止百度爬取`/redirect/`这类中转目录。对于“赞助商推荐”模块，建议使用`<link rel="sponsored">`（百度已支持该属性），明确标注链接的商业性质。

## 三、book类站点中哪些链接坚决不能加nofollow？

虽然nofollow在很多场景下是利器，但滥用同样会伤害SEO。对于book类跨境电商站，以下链接务必保持“follow”状态：

- **核心产品页之间的内链**：比如“购买此书的用户也买了”模块中的链接，如果加nofollow，等于切断了产品页之间的权重传递，不利于长尾词排名。
- **分类导航与面包屑导航**：这些链接是百度理解网站结构的骨架，必须保持follow，才能让蜘蛛顺利爬取所有分类。
- **权威的外部引用链接**：如果你的book页面引用了维基百科、权威出版社或学术机构的资料，这些外链不应加nofollow，因为它们能提升你页面的可信度。

一个更精细化的做法是：对于“相关文章”或“延伸阅读”模块，如果链接指向的是站内高价值内容（如作者专访、专业书评），建议保持follow；如果指向的是泛化内容（如“其他用户的书架”），则可以考虑加nofollow。

## 四、实操：如何在百度SEO框架下部署nofollow标签？

部署nofollow并不只是给链接加一个属性那么简单，它需要与百度蜘蛛的抓取习惯配合。以下是三个实操要点：

**第一，区分“全局nofollow”与“精准nofollow”。** 有些CMS系统（如Shopify、WooCommerce）提供了“所有外链加nofollow”的全局设置，但这会导致你的友情链接、合作伙伴链接也无法传递权重。更建议使用插件或手动代码，只对特定类别的链接（如UGC链接、广告链接）加nofollow。比如，在WordPress中，可以通过`add_filter(‘the_content’, ‘my_nofollow_external_links’)`函数，只对外部链接添加nofollow，而保留内部链接的follow状态。

**第二，利用百度搜索资源平台的“抓取诊断”工具验证效果。** 添加nofollow后，可以提交一批带有nofollow的页面URL，观察百度蜘蛛是否减少了对这些页面的抓取频率。如果发现核心产品页的抓取次数明显增加，说明nofollow策略有效。反之，如果站内有些重要链接（如产品详情页的“作者简介”链接）被误加了nofollow，就要及时调整。

**第三，注意移动端与PC端的nofollow一致性。** 许多book类站点的移动端为了简化页面，可能会遗漏nofollow标签。建议在移动端模板中同样部署nofollow逻辑，避免百度移动端爬虫（如Spider for Mobile）抓取到未标记的链接。

## 总结

**百度SEO针对跨境电商的book** 的优化，本质上是一场“权重分配的艺术”。nofollow标签不是用来“屏蔽”链接的，而是用来“引导”百度蜘蛛的——让它在你的站内，把有限的时间和资源花在最能产生价值的地方。对于book类站点，尤其要警惕UGC链接、功能页面链接和付费链接的权重泄漏，同时守护好核心产品页之间的内链。当你能够精准控制每一个链接的权重流向时，你会发现：即使不增加外链，整站的SEO效果也会迎来明显提升。记住，在百度的世界里，专注比分散更有力量。

## 相关链接

- [http://www.blog.kjbje.cn/Article/details/857964.sHtML](http://www.blog.kjbje.cn/Article/details/857964.sHtML)
- [http://www.blog.kjbje.cn/Article/details/116791.sHtML](http://www.blog.kjbje.cn/Article/details/116791.sHtML)
- [http://www.blog.kjbje.cn/Article/details/245661.sHtML](http://www.blog.kjbje.cn/Article/details/245661.sHtML)
- [http://www.blog.kjbje.cn/Article/details/084644.sHtML](http://www.blog.kjbje.cn/Article/details/084644.sHtML)
- [http://www.blog.kjbje.cn/Article/details/726686.sHtML](http://www.blog.kjbje.cn/Article/details/726686.sHtML)
- [http://www.blog.kjbje.cn/Article/details/490423.sHtML](http://www.blog.kjbje.cn/Article/details/490423.sHtML)
- [http://www.blog.kjbje.cn/Article/details/678818.sHtML](http://www.blog.kjbje.cn/Article/details/678818.sHtML)
- [http://www.blog.kjbje.cn/Article/details/671388.sHtML](http://www.blog.kjbje.cn/Article/details/671388.sHtML)
- [http://www.blog.kjbje.cn/Article/details/768237.sHtML](http://www.blog.kjbje.cn/Article/details/768237.sHtML)
- [http://www.blog.kjbje.cn/Article/details/484406.sHtML](http://www.blog.kjbje.cn/Article/details/484406.sHtML)
- [http://www.blog.kjbje.cn/Article/details/848789.sHtML](http://www.blog.kjbje.cn/Article/details/848789.sHtML)
- [http://www.blog.kjbje.cn/Article/details/197509.sHtML](http://www.blog.kjbje.cn/Article/details/197509.sHtML)
- [http://www.blog.kjbje.cn/Article/details/796850.sHtML](http://www.blog.kjbje.cn/Article/details/796850.sHtML)
- [http://www.blog.kjbje.cn/Article/details/899706.sHtML](http://www.blog.kjbje.cn/Article/details/899706.sHtML)
- [http://www.blog.kjbje.cn/Article/details/559312.sHtML](http://www.blog.kjbje.cn/Article/details/559312.sHtML)
- [http://www.blog.kjbje.cn/Article/details/968075.sHtML](http://www.blog.kjbje.cn/Article/details/968075.sHtML)
- [http://www.blog.kjbje.cn/Article/details/926196.sHtML](http://www.blog.kjbje.cn/Article/details/926196.sHtML)
- [http://www.blog.kjbje.cn/Article/details/715741.sHtML](http://www.blog.kjbje.cn/Article/details/715741.sHtML)
- [http://www.blog.kjbje.cn/Article/details/640464.sHtML](http://www.blog.kjbje.cn/Article/details/640464.sHtML)
- [http://www.blog.kjbje.cn/Article/details/734697.sHtML](http://www.blog.kjbje.cn/Article/details/734697.sHtML)
- [http://www.blog.kjbje.cn/Article/details/576063.sHtML](http://www.blog.kjbje.cn/Article/details/576063.sHtML)
- [http://www.blog.kjbje.cn/Article/details/348003.sHtML](http://www.blog.kjbje.cn/Article/details/348003.sHtML)
- [http://www.blog.kjbje.cn/Article/details/112423.sHtML](http://www.blog.kjbje.cn/Article/details/112423.sHtML)
- [http://www.blog.kjbje.cn/Article/details/857654.sHtML](http://www.blog.kjbje.cn/Article/details/857654.sHtML)
- [http://www.blog.kjbje.cn/Article/details/299605.sHtML](http://www.blog.kjbje.cn/Article/details/299605.sHtML)
- [http://www.blog.kjbje.cn/Article/details/160628.sHtML](http://www.blog.kjbje.cn/Article/details/160628.sHtML)
- [http://www.blog.kjbje.cn/Article/details/264368.sHtML](http://www.blog.kjbje.cn/Article/details/264368.sHtML)
- [http://www.blog.kjbje.cn/Article/details/783144.sHtML](http://www.blog.kjbje.cn/Article/details/783144.sHtML)
- [http://www.blog.kjbje.cn/Article/details/614787.sHtML](http://www.blog.kjbje.cn/Article/details/614787.sHtML)
- [http://www.blog.kjbje.cn/Article/details/699098.sHtML](http://www.blog.kjbje.cn/Article/details/699098.sHtML)
- [http://www.blog.kjbje.cn/Article/details/490730.sHtML](http://www.blog.kjbje.cn/Article/details/490730.sHtML)
- [http://www.blog.kjbje.cn/Article/details/487473.sHtML](http://www.blog.kjbje.cn/Article/details/487473.sHtML)
- [http://www.blog.kjbje.cn/Article/details/938438.sHtML](http://www.blog.kjbje.cn/Article/details/938438.sHtML)
- [http://www.blog.kjbje.cn/Article/details/376395.sHtML](http://www.blog.kjbje.cn/Article/details/376395.sHtML)
- [http://www.blog.kjbje.cn/Article/details/231891.sHtML](http://www.blog.kjbje.cn/Article/details/231891.sHtML)
- [http://www.blog.kjbje.cn/Article/details/170450.sHtML](http://www.blog.kjbje.cn/Article/details/170450.sHtML)
- [http://www.blog.kjbje.cn/Article/details/795816.sHtML](http://www.blog.kjbje.cn/Article/details/795816.sHtML)
- [http://www.blog.kjbje.cn/Article/details/754137.sHtML](http://www.blog.kjbje.cn/Article/details/754137.sHtML)
- [http://www.blog.kjbje.cn/Article/details/222712.sHtML](http://www.blog.kjbje.cn/Article/details/222712.sHtML)
- [http://www.blog.kjbje.cn/Article/details/334032.sHtML](http://www.blog.kjbje.cn/Article/details/334032.sHtML)
- [http://www.blog.kjbje.cn/Article/details/997772.sHtML](http://www.blog.kjbje.cn/Article/details/997772.sHtML)
- [http://www.blog.kjbje.cn/Article/details/511627.sHtML](http://www.blog.kjbje.cn/Article/details/511627.sHtML)
- [http://www.blog.kjbje.cn/Article/details/103566.sHtML](http://www.blog.kjbje.cn/Article/details/103566.sHtML)
- [http://www.blog.kjbje.cn/Article/details/695632.sHtML](http://www.blog.kjbje.cn/Article/details/695632.sHtML)
- [http://www.blog.kjbje.cn/Article/details/200390.sHtML](http://www.blog.kjbje.cn/Article/details/200390.sHtML)
- [http://www.blog.kjbje.cn/Article/details/919006.sHtML](http://www.blog.kjbje.cn/Article/details/919006.sHtML)
- [http://www.blog.kjbje.cn/Article/details/425626.sHtML](http://www.blog.kjbje.cn/Article/details/425626.sHtML)
- [http://www.blog.kjbje.cn/Article/details/632476.sHtML](http://www.blog.kjbje.cn/Article/details/632476.sHtML)
- [http://www.blog.kjbje.cn/Article/details/594801.sHtML](http://www.blog.kjbje.cn/Article/details/594801.sHtML)
- [http://www.blog.kjbje.cn/Article/details/590371.sHtML](http://www.blog.kjbje.cn/Article/details/590371.sHtML)
- [http://www.blog.kjbje.cn/Article/details/049694.sHtML](http://www.blog.kjbje.cn/Article/details/049694.sHtML)
- [http://www.blog.kjbje.cn/Article/details/149095.sHtML](http://www.blog.kjbje.cn/Article/details/149095.sHtML)
- [http://www.blog.kjbje.cn/Article/details/454735.sHtML](http://www.blog.kjbje.cn/Article/details/454735.sHtML)
- [http://www.blog.kjbje.cn/Article/details/043122.sHtML](http://www.blog.kjbje.cn/Article/details/043122.sHtML)
- [http://www.blog.kjbje.cn/Article/details/185417.sHtML](http://www.blog.kjbje.cn/Article/details/185417.sHtML)
- [http://www.blog.kjbje.cn/Article/details/717198.sHtML](http://www.blog.kjbje.cn/Article/details/717198.sHtML)
- [http://www.blog.kjbje.cn/Article/details/142169.sHtML](http://www.blog.kjbje.cn/Article/details/142169.sHtML)
- [http://www.blog.kjbje.cn/Article/details/041405.sHtML](http://www.blog.kjbje.cn/Article/details/041405.sHtML)
- [http://www.blog.kjbje.cn/Article/details/507597.sHtML](http://www.blog.kjbje.cn/Article/details/507597.sHtML)
- [http://www.blog.kjbje.cn/Article/details/672391.sHtML](http://www.blog.kjbje.cn/Article/details/672391.sHtML)
- [http://www.blog.kjbje.cn/Article/details/939538.sHtML](http://www.blog.kjbje.cn/Article/details/939538.sHtML)
- [http://www.blog.kjbje.cn/Article/details/982542.sHtML](http://www.blog.kjbje.cn/Article/details/982542.sHtML)
- [http://www.blog.kjbje.cn/Article/details/779505.sHtML](http://www.blog.kjbje.cn/Article/details/779505.sHtML)
- [http://www.blog.kjbje.cn/Article/details/505052.sHtML](http://www.blog.kjbje.cn/Article/details/505052.sHtML)
- [http://www.blog.kjbje.cn/Article/details/107582.sHtML](http://www.blog.kjbje.cn/Article/details/107582.sHtML)
- [http://www.blog.kjbje.cn/Article/details/696001.sHtML](http://www.blog.kjbje.cn/Article/details/696001.sHtML)
- [http://www.blog.kjbje.cn/Article/details/365346.sHtML](http://www.blog.kjbje.cn/Article/details/365346.sHtML)
- [http://www.blog.kjbje.cn/Article/details/213161.sHtML](http://www.blog.kjbje.cn/Article/details/213161.sHtML)
- [http://www.blog.kjbje.cn/Article/details/387969.sHtML](http://www.blog.kjbje.cn/Article/details/387969.sHtML)
- [http://www.blog.kjbje.cn/Article/details/025330.sHtML](http://www.blog.kjbje.cn/Article/details/025330.sHtML)
- [http://www.blog.kjbje.cn/Article/details/038820.sHtML](http://www.blog.kjbje.cn/Article/details/038820.sHtML)
- [http://www.blog.kjbje.cn/Article/details/311503.sHtML](http://www.blog.kjbje.cn/Article/details/311503.sHtML)
- [http://www.blog.kjbje.cn/Article/details/618426.sHtML](http://www.blog.kjbje.cn/Article/details/618426.sHtML)
- [http://www.blog.kjbje.cn/Article/details/503378.sHtML](http://www.blog.kjbje.cn/Article/details/503378.sHtML)
- [http://www.blog.kjbje.cn/Article/details/366564.sHtML](http://www.blog.kjbje.cn/Article/details/366564.sHtML)
- [http://www.blog.kjbje.cn/Article/details/186796.sHtML](http://www.blog.kjbje.cn/Article/details/186796.sHtML)
- [http://www.blog.kjbje.cn/Article/details/623180.sHtML](http://www.blog.kjbje.cn/Article/details/623180.sHtML)
- [http://www.blog.kjbje.cn/Article/details/968257.sHtML](http://www.blog.kjbje.cn/Article/details/968257.sHtML)
- [http://www.blog.kjbje.cn/Article/details/037670.sHtML](http://www.blog.kjbje.cn/Article/details/037670.sHtML)
- [http://www.blog.kjbje.cn/Article/details/804840.sHtML](http://www.blog.kjbje.cn/Article/details/804840.sHtML)
- [http://www.blog.kjbje.cn/Article/details/236000.sHtML](http://www.blog.kjbje.cn/Article/details/236000.sHtML)
- [http://www.blog.kjbje.cn/Article/details/860932.sHtML](http://www.blog.kjbje.cn/Article/details/860932.sHtML)
- [http://www.blog.kjbje.cn/Article/details/447626.sHtML](http://www.blog.kjbje.cn/Article/details/447626.sHtML)
- [http://www.blog.kjbje.cn/Article/details/488926.sHtML](http://www.blog.kjbje.cn/Article/details/488926.sHtML)
- [http://www.blog.kjbje.cn/Article/details/568396.sHtML](http://www.blog.kjbje.cn/Article/details/568396.sHtML)
- [http://www.blog.kjbje.cn/Article/details/791743.sHtML](http://www.blog.kjbje.cn/Article/details/791743.sHtML)
- [http://www.blog.kjbje.cn/Article/details/131073.sHtML](http://www.blog.kjbje.cn/Article/details/131073.sHtML)
- [http://www.blog.kjbje.cn/Article/details/376569.sHtML](http://www.blog.kjbje.cn/Article/details/376569.sHtML)
- [http://www.blog.kjbje.cn/Article/details/084745.sHtML](http://www.blog.kjbje.cn/Article/details/084745.sHtML)
- [http://www.blog.kjbje.cn/Article/details/229446.sHtML](http://www.blog.kjbje.cn/Article/details/229446.sHtML)
- [http://www.blog.kjbje.cn/Article/details/210111.sHtML](http://www.blog.kjbje.cn/Article/details/210111.sHtML)
- [http://www.blog.kjbje.cn/Article/details/635866.sHtML](http://www.blog.kjbje.cn/Article/details/635866.sHtML)
- [http://www.blog.kjbje.cn/Article/details/042341.sHtML](http://www.blog.kjbje.cn/Article/details/042341.sHtML)
- [http://www.blog.kjbje.cn/Article/details/724924.sHtML](http://www.blog.kjbje.cn/Article/details/724924.sHtML)
- [http://www.blog.kjbje.cn/Article/details/647511.sHtML](http://www.blog.kjbje.cn/Article/details/647511.sHtML)
- [http://www.blog.kjbje.cn/Article/details/343440.sHtML](http://www.blog.kjbje.cn/Article/details/343440.sHtML)
- [http://www.blog.kjbje.cn/Article/details/966709.sHtML](http://www.blog.kjbje.cn/Article/details/966709.sHtML)
- [http://www.blog.kjbje.cn/Article/details/607976.sHtML](http://www.blog.kjbje.cn/Article/details/607976.sHtML)
- [http://www.blog.kjbje.cn/Article/details/802096.sHtML](http://www.blog.kjbje.cn/Article/details/802096.sHtML)
- [http://www.blog.kjbje.cn/Article/details/369897.sHtML](http://www.blog.kjbje.cn/Article/details/369897.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/405507.sHtML](http://www.blog.cvbhg.cn/Article/details/405507.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/909352.sHtML](http://www.blog.cvbhg.cn/Article/details/909352.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/593382.sHtML](http://www.blog.cvbhg.cn/Article/details/593382.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/791269.sHtML](http://www.blog.cvbhg.cn/Article/details/791269.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/170641.sHtML](http://www.blog.cvbhg.cn/Article/details/170641.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/168823.sHtML](http://www.blog.cvbhg.cn/Article/details/168823.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/033750.sHtML](http://www.blog.cvbhg.cn/Article/details/033750.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/240907.sHtML](http://www.blog.cvbhg.cn/Article/details/240907.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/444355.sHtML](http://www.blog.cvbhg.cn/Article/details/444355.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/979850.sHtML](http://www.blog.cvbhg.cn/Article/details/979850.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/329900.sHtML](http://www.blog.cvbhg.cn/Article/details/329900.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/344048.sHtML](http://www.blog.cvbhg.cn/Article/details/344048.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/032064.sHtML](http://www.blog.cvbhg.cn/Article/details/032064.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/519252.sHtML](http://www.blog.cvbhg.cn/Article/details/519252.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/260531.sHtML](http://www.blog.cvbhg.cn/Article/details/260531.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/614166.sHtML](http://www.blog.cvbhg.cn/Article/details/614166.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/677912.sHtML](http://www.blog.cvbhg.cn/Article/details/677912.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/115654.sHtML](http://www.blog.cvbhg.cn/Article/details/115654.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/726947.sHtML](http://www.blog.cvbhg.cn/Article/details/726947.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/295520.sHtML](http://www.blog.cvbhg.cn/Article/details/295520.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/814604.sHtML](http://www.blog.cvbhg.cn/Article/details/814604.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/408521.sHtML](http://www.blog.cvbhg.cn/Article/details/408521.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/579736.sHtML](http://www.blog.cvbhg.cn/Article/details/579736.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/854871.sHtML](http://www.blog.cvbhg.cn/Article/details/854871.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/612241.sHtML](http://www.blog.cvbhg.cn/Article/details/612241.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/830366.sHtML](http://www.blog.cvbhg.cn/Article/details/830366.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/798625.sHtML](http://www.blog.cvbhg.cn/Article/details/798625.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/705094.sHtML](http://www.blog.cvbhg.cn/Article/details/705094.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/967967.sHtML](http://www.blog.cvbhg.cn/Article/details/967967.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/312859.sHtML](http://www.blog.cvbhg.cn/Article/details/312859.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/976874.sHtML](http://www.blog.cvbhg.cn/Article/details/976874.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/065912.sHtML](http://www.blog.cvbhg.cn/Article/details/065912.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/890327.sHtML](http://www.blog.cvbhg.cn/Article/details/890327.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/286422.sHtML](http://www.blog.cvbhg.cn/Article/details/286422.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/069739.sHtML](http://www.blog.cvbhg.cn/Article/details/069739.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/834016.sHtML](http://www.blog.cvbhg.cn/Article/details/834016.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/489674.sHtML](http://www.blog.cvbhg.cn/Article/details/489674.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/235419.sHtML](http://www.blog.cvbhg.cn/Article/details/235419.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/388112.sHtML](http://www.blog.cvbhg.cn/Article/details/388112.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/400374.sHtML](http://www.blog.cvbhg.cn/Article/details/400374.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/720578.sHtML](http://www.blog.cvbhg.cn/Article/details/720578.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/958845.sHtML](http://www.blog.cvbhg.cn/Article/details/958845.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/114874.sHtML](http://www.blog.cvbhg.cn/Article/details/114874.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/192781.sHtML](http://www.blog.cvbhg.cn/Article/details/192781.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/937161.sHtML](http://www.blog.cvbhg.cn/Article/details/937161.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/691252.sHtML](http://www.blog.cvbhg.cn/Article/details/691252.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/898332.sHtML](http://www.blog.cvbhg.cn/Article/details/898332.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/574216.sHtML](http://www.blog.cvbhg.cn/Article/details/574216.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/343557.sHtML](http://www.blog.cvbhg.cn/Article/details/343557.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/460481.sHtML](http://www.blog.cvbhg.cn/Article/details/460481.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/752823.sHtML](http://www.blog.cvbhg.cn/Article/details/752823.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/548753.sHtML](http://www.blog.cvbhg.cn/Article/details/548753.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/595447.sHtML](http://www.blog.cvbhg.cn/Article/details/595447.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/858488.sHtML](http://www.blog.cvbhg.cn/Article/details/858488.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/017743.sHtML](http://www.blog.cvbhg.cn/Article/details/017743.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/926490.sHtML](http://www.blog.cvbhg.cn/Article/details/926490.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/579734.sHtML](http://www.blog.cvbhg.cn/Article/details/579734.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/800160.sHtML](http://www.blog.cvbhg.cn/Article/details/800160.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/888084.sHtML](http://www.blog.cvbhg.cn/Article/details/888084.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/241828.sHtML](http://www.blog.cvbhg.cn/Article/details/241828.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/812231.sHtML](http://www.blog.cvbhg.cn/Article/details/812231.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/064234.sHtML](http://www.blog.cvbhg.cn/Article/details/064234.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/655440.sHtML](http://www.blog.cvbhg.cn/Article/details/655440.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/063826.sHtML](http://www.blog.cvbhg.cn/Article/details/063826.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/822074.sHtML](http://www.blog.cvbhg.cn/Article/details/822074.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/034285.sHtML](http://www.blog.cvbhg.cn/Article/details/034285.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/352362.sHtML](http://www.blog.cvbhg.cn/Article/details/352362.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/549883.sHtML](http://www.blog.cvbhg.cn/Article/details/549883.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/152537.sHtML](http://www.blog.cvbhg.cn/Article/details/152537.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/506413.sHtML](http://www.blog.cvbhg.cn/Article/details/506413.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/964644.sHtML](http://www.blog.cvbhg.cn/Article/details/964644.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/461891.sHtML](http://www.blog.cvbhg.cn/Article/details/461891.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/596051.sHtML](http://www.blog.cvbhg.cn/Article/details/596051.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/895279.sHtML](http://www.blog.cvbhg.cn/Article/details/895279.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/208174.sHtML](http://www.blog.cvbhg.cn/Article/details/208174.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/062935.sHtML](http://www.blog.cvbhg.cn/Article/details/062935.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/653644.sHtML](http://www.blog.cvbhg.cn/Article/details/653644.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/975639.sHtML](http://www.blog.cvbhg.cn/Article/details/975639.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/779464.sHtML](http://www.blog.cvbhg.cn/Article/details/779464.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/933155.sHtML](http://www.blog.cvbhg.cn/Article/details/933155.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/914696.sHtML](http://www.blog.cvbhg.cn/Article/details/914696.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/737217.sHtML](http://www.blog.cvbhg.cn/Article/details/737217.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/935384.sHtML](http://www.blog.cvbhg.cn/Article/details/935384.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/371063.sHtML](http://www.blog.cvbhg.cn/Article/details/371063.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/700589.sHtML](http://www.blog.cvbhg.cn/Article/details/700589.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/876232.sHtML](http://www.blog.cvbhg.cn/Article/details/876232.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/221300.sHtML](http://www.blog.cvbhg.cn/Article/details/221300.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/099445.sHtML](http://www.blog.cvbhg.cn/Article/details/099445.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/200000.sHtML](http://www.blog.cvbhg.cn/Article/details/200000.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/958112.sHtML](http://www.blog.cvbhg.cn/Article/details/958112.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/888564.sHtML](http://www.blog.cvbhg.cn/Article/details/888564.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/271594.sHtML](http://www.blog.cvbhg.cn/Article/details/271594.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/243598.sHtML](http://www.blog.cvbhg.cn/Article/details/243598.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/255365.sHtML](http://www.blog.cvbhg.cn/Article/details/255365.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/813248.sHtML](http://www.blog.cvbhg.cn/Article/details/813248.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/361669.sHtML](http://www.blog.cvbhg.cn/Article/details/361669.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/176832.sHtML](http://www.blog.cvbhg.cn/Article/details/176832.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/826062.sHtML](http://www.blog.cvbhg.cn/Article/details/826062.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/296724.sHtML](http://www.blog.cvbhg.cn/Article/details/296724.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/060429.sHtML](http://www.blog.cvbhg.cn/Article/details/060429.sHtML)
