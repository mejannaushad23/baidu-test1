# 百度SEO针对跨境电商book的nofollow标签使用场景：精准控制抓取，提升站内权重

对于运营跨境电商book类网站（无论是销售电子书、实体教材、儿童绘本，还是提供学术资源订阅）的站长来说，**百度SEO针对跨境电商的book** 优化不仅关乎关键词排名，更涉及站内资源的有效分配。一个常被忽视但极其重要的技术细节，就是 `nofollow` 标签的正确使用。很多跨境BOOK站因为盲目添加或遗漏nofollow，导致百度蜘蛛被无效链接消耗，真正有价值的产品页反而得不到充分抓取。本文将从实际场景出发，详细拆解 nolollow 标签在跨境电商BOOK网站中的具体应用策略。

## 一、为什么跨境电商BOOK站需要重视nofollow标签？

百度蜘蛛抓取资源有限，尤其是对于内容密集型、多语言、多分类的跨境电商BOOK网站。如果站内存在大量低质量或非核心链接（如用户评论区的垃圾外链、重复的筛选参数URL、支付跳转页面），蜘蛛爬行时就会被“带偏”，无法高效索引你希望被收录的产品详情页和核心书籍内容。

**百度SEO针对跨境电商的book** 优化核心逻辑是：引导蜘蛛优先抓取“高价值页面”（如书籍详情、分类聚合页、品牌故事页），屏蔽“低价值或风险页面”（如购物车、登录注册、外部跳转链接）。nofollow 标签就是实现这一目标的最直接工具——它告诉百度：“这个链接不需要传递权重，也不需要重点抓取。”

## 二、nofollow在跨境电商BOOK站的主要使用场景

### 1. 屏蔽用户生成内容（UGC）中的外部链接

跨境BOOK站通常设有评论区、问答区或用户书评板块。这些区域极易被垃圾评论机器人攻击，留下大量指向竞品或低质量网站的链接。如果不加处理，百度会将这些外链视为站内推荐，导致权重流失甚至被判定为“外链农场”。

**最佳实践：** 对所有用户提交的链接（包括评论中的URL、用户简介中的网址）自动添加 `rel=“nofollow”`。同时，对“作者回复”中的外部链接也建议加nofollow，除非该链接是官方合作资源。例如，在用户“John”的评论中，他留下的个人博客链接，必须用nofollow阻断权重传递。

### 2. 处理筛选、排序和分页中的重复参数链接

跨境电商BOOK站常有按“价格、出版日期、评分”排序的筛选功能。这些链接通常包含大量参数（如 `?sort=price&order=asc&page=2`），且内容与默认排序页面高度重复。百度蜘蛛如果频繁抓取这些参数化URL，会浪费大量配额，且可能导致重复内容惩罚。

**最佳实践：** 
- 对“按销量/价格/出版年份”排序的链接，使用 `rel=“nofollow”` 或直接通过 robots.txt 屏蔽。
- 对于分页链接（第2页、第3页），**不建议**全局加nofollow，而是通过 `canonical` 标签指向首页，并在第2页及以后的分页链接上添加 `rel=“nofollow”`（除非你有明确的SEO策略需要分页传递权重）。
- 对于“筛选分类+价格区间”生成的动态链接（如 `?category=fiction&price=10-20`），同样建议加nofollow，因为这些页面内容与固定分类页高度相似。

### 3. 支付流程、登录注册及用户中心页面

跨境BOOK站的购物车、结账页面、登录/注册页面、用户订单历史等，是典型的“功能页面”。这些页面不仅不需要被索引，而且一旦被收录，可能泄露用户隐私或导致转化路径被蜘蛛干扰。

**最佳实践：** 
- 对“加入购物车”按钮的链接、结算页面的链接、“我的账户”链接，全部使用 `rel=“nofollow”`。
- 对于“忘记密码”“退换货申请”等辅助功能链接，同样加nofollow。
- 注意：**不要**给“产品详情页的‘添加到购物车’按钮”加nofollow，因为该按钮通常是一个表单提交或JavaScript触发事件，不是真正的外部链接。需要加nofollow的是指向购物车页面的 `<a>` 标签链接。

### 4. 社交分享、外部合作伙伴及广告链接

很多跨境BOOK站会在产品页放置“分享到Facebook/Twitter/Pinterest”的按钮，或底部有“友情链接”“合作伙伴”版块。这些外部链接如果传递权重，会分散站内资源。

**最佳实践：** 
- 所有社交分享图标（Facebook、Twitter、LinkedIn等）的链接，一律加 `rel=“nofollow noopener”`。这既阻断权重传递，也提升安全。
- 合作伙伴友情链接：如果是付费广告或非核心资源，务必加nofollow；如果是战略合作（如与出版社的互相推荐链接），可以根据情况决定是否传递权重，但建议初期先加nofollow，观察百度反应。
- “购买本书”跳转到第三方平台（如Amazon、eBay）的链接：**必须加nofollow**，因为这是将用户导出站外，百度不应认为你推荐了外部网站。

### 5. 标签云、热门搜索词及“相关产品”推荐

跨境BOOK站常使用标签云（如“科幻小说”“2024年新书”）或“你可能也喜欢”模块。这些链接虽然指向站内页面，但存在两个风险：一是标签数量过多，导致蜘蛛抓取过多低价值页面；二是“相关产品”推荐链接如果基于算法生成，可能指向不相关或低权重页面。

**最佳实践：** 
- 对于标签云中的链接：如果标签页没有独立内容（仅列出书籍列表），建议加nofollow；如果标签页有精心编辑的介绍、SEO标题和独特内容，可以保留follow。
- 对于“相关产品”推荐模块：建议只对“展示在当前页面下方”的链接加nofollow，因为这些链接的目的是提升用户浏览，而非SEO权重传递。核心产品详情页的内链，应主要通过面包屑导航、分类导航和正文中的相关链接传递。

## 三、实施nofollow时需避免的常见错误

### 1. 对站内核心导航链接加nofollow
有些站长为了防止权重分散，对“分类目录”“关于我们”“联系方式”也加nofollow。这是**致命错误**。这些导航页面是网站结构的重要组成部分，需要权重传递来提升收录和排名。**百度SEO针对跨境电商的book** 优化的前提是：站内核心导航、分类页、产品页必须“follow”，让蜘蛛顺畅爬行。

### 2. 过度使用nofollow导致内链断裂
比如，你给“所有分页链接”都加了nofollow，但本身没有其他内链指向第2页及以后的内容，那么这些页面可能永远无法被蜘蛛发现。正确的做法是：在首页或分类页的“加载更多”按钮中，用JavaScript异步加载内容，或保留部分分页链接不带nofollow，同时通过 `canonical` 和 `prev/next` 标签规范分页关系。

### 3. 忽略nofollow对权重传递的影响
nofollow 标签阻止的是“权重传递”和“抓取路径”，但**不阻止链接被点击**。用户仍然可以通过nofollow链接访问页面。因此，不要以为加了nofollow就能完全隐藏链接——百度仍可能通过用户的点击行为（如用户从站外带链接进入）发现该页面。如果页面本身质量低，建议同时使用 `noindex` 标签彻底禁止索引。

## 四、如何通过nofollow提升BOOK站的百度收录效率？

一个典型的跨境BOOK站，可能有数万甚至数百万个产品页面。合理使用nofollow，能让百度蜘蛛将有限的资源集中在“流量转化”页面上：

1. **优先抓取“书籍详情页”**：确保产品详情页的链接（从分类页、搜索页、首页指向详情页）全部为“follow”，且路径简洁。
2. **阻断“低价值入口”**：用nofollow屏蔽所有筛选参数、标签云、用户评论中的外链，让蜘蛛从分类页直接进入详情页，而不是重复抓取同一产品的不同参数版本。
3. **结构化数据与nofollow配合**：在书籍详情页的 `script` 标签中标注 `Book` 结构化数据，同时确保该页面没有任何nofollow的内链（除了功能链接）。这样百度在提取结构化数据时，也能通过跟随内链发现更多相关书籍。

举个例子：一个销售英文原版童书的跨境站，将“按年龄段筛选”的链接全部加nofollow，同时保留“3-5岁绘本”“6-8岁桥梁书”等分类页的follow。蜘蛛抓取首页后，会优先抓取这些分类页，再通过分类页进入具体书籍详情页，而不会浪费配额去抓取 `?age=3-5&sort=price` 这种动态链接。

## 五、总结：nofollow是精细化SEO的“剪刀手”

对于跨境BOOK站而言，nofollow不是“禁用链接”，而是“优化链接”。**百度SEO针对跨境电商的book** 的最终目标，不是让百度抓取站内所有页面，而是让百度抓取“最应该被收录的页面”。通过精准使用nofollow，你可以像剪刀手一样，剪掉那些冗余的、重复的、风险的链接，让蜘蛛沿着你设计的路径，高效地收录你的产品目录、书籍介绍和品牌内容。

记住一个原则：每一条链接都有成本。在跨境BOOK站中，用户评论区的垃圾链接、筛选参数链接、第三方支付跳转链接，都是“隐形成本”。用nofollow主动管理这些成本，你的网站才能把有限的权重集中在真正能产生订单的book页面上，最终在百度搜索结果中获得更靠前的位置。

## 相关链接

- [http://www.blog.kjbje.cn/Article/details/361316.sHtML](http://www.blog.kjbje.cn/Article/details/361316.sHtML)
- [http://www.blog.kjbje.cn/Article/details/140308.sHtML](http://www.blog.kjbje.cn/Article/details/140308.sHtML)
- [http://www.blog.kjbje.cn/Article/details/103418.sHtML](http://www.blog.kjbje.cn/Article/details/103418.sHtML)
- [http://www.blog.kjbje.cn/Article/details/679810.sHtML](http://www.blog.kjbje.cn/Article/details/679810.sHtML)
- [http://www.blog.kjbje.cn/Article/details/747448.sHtML](http://www.blog.kjbje.cn/Article/details/747448.sHtML)
- [http://www.blog.kjbje.cn/Article/details/723933.sHtML](http://www.blog.kjbje.cn/Article/details/723933.sHtML)
- [http://www.blog.kjbje.cn/Article/details/767209.sHtML](http://www.blog.kjbje.cn/Article/details/767209.sHtML)
- [http://www.blog.kjbje.cn/Article/details/369858.sHtML](http://www.blog.kjbje.cn/Article/details/369858.sHtML)
- [http://www.blog.kjbje.cn/Article/details/054231.sHtML](http://www.blog.kjbje.cn/Article/details/054231.sHtML)
- [http://www.blog.kjbje.cn/Article/details/396456.sHtML](http://www.blog.kjbje.cn/Article/details/396456.sHtML)
- [http://www.blog.kjbje.cn/Article/details/336943.sHtML](http://www.blog.kjbje.cn/Article/details/336943.sHtML)
- [http://www.blog.kjbje.cn/Article/details/116348.sHtML](http://www.blog.kjbje.cn/Article/details/116348.sHtML)
- [http://www.blog.kjbje.cn/Article/details/175556.sHtML](http://www.blog.kjbje.cn/Article/details/175556.sHtML)
- [http://www.blog.kjbje.cn/Article/details/452788.sHtML](http://www.blog.kjbje.cn/Article/details/452788.sHtML)
- [http://www.blog.kjbje.cn/Article/details/034325.sHtML](http://www.blog.kjbje.cn/Article/details/034325.sHtML)
- [http://www.blog.kjbje.cn/Article/details/307280.sHtML](http://www.blog.kjbje.cn/Article/details/307280.sHtML)
- [http://www.blog.kjbje.cn/Article/details/912787.sHtML](http://www.blog.kjbje.cn/Article/details/912787.sHtML)
- [http://www.blog.kjbje.cn/Article/details/091529.sHtML](http://www.blog.kjbje.cn/Article/details/091529.sHtML)
- [http://www.blog.kjbje.cn/Article/details/848420.sHtML](http://www.blog.kjbje.cn/Article/details/848420.sHtML)
- [http://www.blog.kjbje.cn/Article/details/095774.sHtML](http://www.blog.kjbje.cn/Article/details/095774.sHtML)
- [http://www.blog.kjbje.cn/Article/details/943572.sHtML](http://www.blog.kjbje.cn/Article/details/943572.sHtML)
- [http://www.blog.kjbje.cn/Article/details/957715.sHtML](http://www.blog.kjbje.cn/Article/details/957715.sHtML)
- [http://www.blog.kjbje.cn/Article/details/410244.sHtML](http://www.blog.kjbje.cn/Article/details/410244.sHtML)
- [http://www.blog.kjbje.cn/Article/details/749588.sHtML](http://www.blog.kjbje.cn/Article/details/749588.sHtML)
- [http://www.blog.kjbje.cn/Article/details/046535.sHtML](http://www.blog.kjbje.cn/Article/details/046535.sHtML)
- [http://www.blog.kjbje.cn/Article/details/153427.sHtML](http://www.blog.kjbje.cn/Article/details/153427.sHtML)
- [http://www.blog.kjbje.cn/Article/details/867461.sHtML](http://www.blog.kjbje.cn/Article/details/867461.sHtML)
- [http://www.blog.kjbje.cn/Article/details/379230.sHtML](http://www.blog.kjbje.cn/Article/details/379230.sHtML)
- [http://www.blog.kjbje.cn/Article/details/548029.sHtML](http://www.blog.kjbje.cn/Article/details/548029.sHtML)
- [http://www.blog.kjbje.cn/Article/details/297160.sHtML](http://www.blog.kjbje.cn/Article/details/297160.sHtML)
- [http://www.blog.kjbje.cn/Article/details/469296.sHtML](http://www.blog.kjbje.cn/Article/details/469296.sHtML)
- [http://www.blog.kjbje.cn/Article/details/143901.sHtML](http://www.blog.kjbje.cn/Article/details/143901.sHtML)
- [http://www.blog.kjbje.cn/Article/details/018474.sHtML](http://www.blog.kjbje.cn/Article/details/018474.sHtML)
- [http://www.blog.kjbje.cn/Article/details/035189.sHtML](http://www.blog.kjbje.cn/Article/details/035189.sHtML)
- [http://www.blog.kjbje.cn/Article/details/067966.sHtML](http://www.blog.kjbje.cn/Article/details/067966.sHtML)
- [http://www.blog.kjbje.cn/Article/details/662045.sHtML](http://www.blog.kjbje.cn/Article/details/662045.sHtML)
- [http://www.blog.kjbje.cn/Article/details/077650.sHtML](http://www.blog.kjbje.cn/Article/details/077650.sHtML)
- [http://www.blog.kjbje.cn/Article/details/157478.sHtML](http://www.blog.kjbje.cn/Article/details/157478.sHtML)
- [http://www.blog.kjbje.cn/Article/details/104013.sHtML](http://www.blog.kjbje.cn/Article/details/104013.sHtML)
- [http://www.blog.kjbje.cn/Article/details/813013.sHtML](http://www.blog.kjbje.cn/Article/details/813013.sHtML)
- [http://www.blog.kjbje.cn/Article/details/497734.sHtML](http://www.blog.kjbje.cn/Article/details/497734.sHtML)
- [http://www.blog.kjbje.cn/Article/details/398955.sHtML](http://www.blog.kjbje.cn/Article/details/398955.sHtML)
- [http://www.blog.kjbje.cn/Article/details/864240.sHtML](http://www.blog.kjbje.cn/Article/details/864240.sHtML)
- [http://www.blog.kjbje.cn/Article/details/948055.sHtML](http://www.blog.kjbje.cn/Article/details/948055.sHtML)
- [http://www.blog.kjbje.cn/Article/details/285796.sHtML](http://www.blog.kjbje.cn/Article/details/285796.sHtML)
- [http://www.blog.kjbje.cn/Article/details/252576.sHtML](http://www.blog.kjbje.cn/Article/details/252576.sHtML)
- [http://www.blog.kjbje.cn/Article/details/033344.sHtML](http://www.blog.kjbje.cn/Article/details/033344.sHtML)
- [http://www.blog.kjbje.cn/Article/details/366251.sHtML](http://www.blog.kjbje.cn/Article/details/366251.sHtML)
- [http://www.blog.kjbje.cn/Article/details/306970.sHtML](http://www.blog.kjbje.cn/Article/details/306970.sHtML)
- [http://www.blog.kjbje.cn/Article/details/207316.sHtML](http://www.blog.kjbje.cn/Article/details/207316.sHtML)
- [http://www.blog.kjbje.cn/Article/details/163730.sHtML](http://www.blog.kjbje.cn/Article/details/163730.sHtML)
- [http://www.blog.kjbje.cn/Article/details/240470.sHtML](http://www.blog.kjbje.cn/Article/details/240470.sHtML)
- [http://www.blog.kjbje.cn/Article/details/848591.sHtML](http://www.blog.kjbje.cn/Article/details/848591.sHtML)
- [http://www.blog.kjbje.cn/Article/details/845655.sHtML](http://www.blog.kjbje.cn/Article/details/845655.sHtML)
- [http://www.blog.kjbje.cn/Article/details/292023.sHtML](http://www.blog.kjbje.cn/Article/details/292023.sHtML)
- [http://www.blog.kjbje.cn/Article/details/521260.sHtML](http://www.blog.kjbje.cn/Article/details/521260.sHtML)
- [http://www.blog.kjbje.cn/Article/details/654741.sHtML](http://www.blog.kjbje.cn/Article/details/654741.sHtML)
- [http://www.blog.kjbje.cn/Article/details/419816.sHtML](http://www.blog.kjbje.cn/Article/details/419816.sHtML)
- [http://www.blog.kjbje.cn/Article/details/286802.sHtML](http://www.blog.kjbje.cn/Article/details/286802.sHtML)
- [http://www.blog.kjbje.cn/Article/details/330238.sHtML](http://www.blog.kjbje.cn/Article/details/330238.sHtML)
- [http://www.blog.kjbje.cn/Article/details/941236.sHtML](http://www.blog.kjbje.cn/Article/details/941236.sHtML)
- [http://www.blog.kjbje.cn/Article/details/230249.sHtML](http://www.blog.kjbje.cn/Article/details/230249.sHtML)
- [http://www.blog.kjbje.cn/Article/details/037343.sHtML](http://www.blog.kjbje.cn/Article/details/037343.sHtML)
- [http://www.blog.kjbje.cn/Article/details/617901.sHtML](http://www.blog.kjbje.cn/Article/details/617901.sHtML)
- [http://www.blog.kjbje.cn/Article/details/617990.sHtML](http://www.blog.kjbje.cn/Article/details/617990.sHtML)
- [http://www.blog.kjbje.cn/Article/details/899083.sHtML](http://www.blog.kjbje.cn/Article/details/899083.sHtML)
- [http://www.blog.kjbje.cn/Article/details/236524.sHtML](http://www.blog.kjbje.cn/Article/details/236524.sHtML)
- [http://www.blog.kjbje.cn/Article/details/762607.sHtML](http://www.blog.kjbje.cn/Article/details/762607.sHtML)
- [http://www.blog.kjbje.cn/Article/details/169614.sHtML](http://www.blog.kjbje.cn/Article/details/169614.sHtML)
- [http://www.blog.kjbje.cn/Article/details/131715.sHtML](http://www.blog.kjbje.cn/Article/details/131715.sHtML)
- [http://www.blog.kjbje.cn/Article/details/568301.sHtML](http://www.blog.kjbje.cn/Article/details/568301.sHtML)
- [http://www.blog.kjbje.cn/Article/details/612219.sHtML](http://www.blog.kjbje.cn/Article/details/612219.sHtML)
- [http://www.blog.kjbje.cn/Article/details/928467.sHtML](http://www.blog.kjbje.cn/Article/details/928467.sHtML)
- [http://www.blog.kjbje.cn/Article/details/753128.sHtML](http://www.blog.kjbje.cn/Article/details/753128.sHtML)
- [http://www.blog.kjbje.cn/Article/details/001278.sHtML](http://www.blog.kjbje.cn/Article/details/001278.sHtML)
- [http://www.blog.kjbje.cn/Article/details/302022.sHtML](http://www.blog.kjbje.cn/Article/details/302022.sHtML)
- [http://www.blog.kjbje.cn/Article/details/571996.sHtML](http://www.blog.kjbje.cn/Article/details/571996.sHtML)
- [http://www.blog.kjbje.cn/Article/details/669292.sHtML](http://www.blog.kjbje.cn/Article/details/669292.sHtML)
- [http://www.blog.kjbje.cn/Article/details/146045.sHtML](http://www.blog.kjbje.cn/Article/details/146045.sHtML)
- [http://www.blog.kjbje.cn/Article/details/397900.sHtML](http://www.blog.kjbje.cn/Article/details/397900.sHtML)
- [http://www.blog.kjbje.cn/Article/details/754332.sHtML](http://www.blog.kjbje.cn/Article/details/754332.sHtML)
- [http://www.blog.kjbje.cn/Article/details/544083.sHtML](http://www.blog.kjbje.cn/Article/details/544083.sHtML)
- [http://www.blog.kjbje.cn/Article/details/910653.sHtML](http://www.blog.kjbje.cn/Article/details/910653.sHtML)
- [http://www.blog.kjbje.cn/Article/details/558825.sHtML](http://www.blog.kjbje.cn/Article/details/558825.sHtML)
- [http://www.blog.kjbje.cn/Article/details/509033.sHtML](http://www.blog.kjbje.cn/Article/details/509033.sHtML)
- [http://www.blog.kjbje.cn/Article/details/286878.sHtML](http://www.blog.kjbje.cn/Article/details/286878.sHtML)
- [http://www.blog.kjbje.cn/Article/details/297459.sHtML](http://www.blog.kjbje.cn/Article/details/297459.sHtML)
- [http://www.blog.kjbje.cn/Article/details/851416.sHtML](http://www.blog.kjbje.cn/Article/details/851416.sHtML)
- [http://www.blog.kjbje.cn/Article/details/530538.sHtML](http://www.blog.kjbje.cn/Article/details/530538.sHtML)
- [http://www.blog.kjbje.cn/Article/details/375556.sHtML](http://www.blog.kjbje.cn/Article/details/375556.sHtML)
- [http://www.blog.kjbje.cn/Article/details/267390.sHtML](http://www.blog.kjbje.cn/Article/details/267390.sHtML)
- [http://www.blog.kjbje.cn/Article/details/589534.sHtML](http://www.blog.kjbje.cn/Article/details/589534.sHtML)
- [http://www.blog.kjbje.cn/Article/details/908038.sHtML](http://www.blog.kjbje.cn/Article/details/908038.sHtML)
- [http://www.blog.kjbje.cn/Article/details/540242.sHtML](http://www.blog.kjbje.cn/Article/details/540242.sHtML)
- [http://www.blog.kjbje.cn/Article/details/117964.sHtML](http://www.blog.kjbje.cn/Article/details/117964.sHtML)
- [http://www.blog.kjbje.cn/Article/details/606114.sHtML](http://www.blog.kjbje.cn/Article/details/606114.sHtML)
- [http://www.blog.kjbje.cn/Article/details/715087.sHtML](http://www.blog.kjbje.cn/Article/details/715087.sHtML)
- [http://www.blog.kjbje.cn/Article/details/316017.sHtML](http://www.blog.kjbje.cn/Article/details/316017.sHtML)
- [http://www.blog.kjbje.cn/Article/details/491099.sHtML](http://www.blog.kjbje.cn/Article/details/491099.sHtML)
- [http://www.blog.kjbje.cn/Article/details/093084.sHtML](http://www.blog.kjbje.cn/Article/details/093084.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/550391.sHtML](http://www.blog.cvbhg.cn/Article/details/550391.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/159853.sHtML](http://www.blog.cvbhg.cn/Article/details/159853.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/008212.sHtML](http://www.blog.cvbhg.cn/Article/details/008212.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/789312.sHtML](http://www.blog.cvbhg.cn/Article/details/789312.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/601160.sHtML](http://www.blog.cvbhg.cn/Article/details/601160.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/680222.sHtML](http://www.blog.cvbhg.cn/Article/details/680222.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/112163.sHtML](http://www.blog.cvbhg.cn/Article/details/112163.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/877679.sHtML](http://www.blog.cvbhg.cn/Article/details/877679.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/625741.sHtML](http://www.blog.cvbhg.cn/Article/details/625741.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/900118.sHtML](http://www.blog.cvbhg.cn/Article/details/900118.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/780995.sHtML](http://www.blog.cvbhg.cn/Article/details/780995.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/830361.sHtML](http://www.blog.cvbhg.cn/Article/details/830361.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/127472.sHtML](http://www.blog.cvbhg.cn/Article/details/127472.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/712051.sHtML](http://www.blog.cvbhg.cn/Article/details/712051.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/061115.sHtML](http://www.blog.cvbhg.cn/Article/details/061115.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/667847.sHtML](http://www.blog.cvbhg.cn/Article/details/667847.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/748181.sHtML](http://www.blog.cvbhg.cn/Article/details/748181.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/554224.sHtML](http://www.blog.cvbhg.cn/Article/details/554224.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/833848.sHtML](http://www.blog.cvbhg.cn/Article/details/833848.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/746044.sHtML](http://www.blog.cvbhg.cn/Article/details/746044.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/194663.sHtML](http://www.blog.cvbhg.cn/Article/details/194663.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/804687.sHtML](http://www.blog.cvbhg.cn/Article/details/804687.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/447626.sHtML](http://www.blog.cvbhg.cn/Article/details/447626.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/710429.sHtML](http://www.blog.cvbhg.cn/Article/details/710429.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/913333.sHtML](http://www.blog.cvbhg.cn/Article/details/913333.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/630806.sHtML](http://www.blog.cvbhg.cn/Article/details/630806.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/867751.sHtML](http://www.blog.cvbhg.cn/Article/details/867751.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/064179.sHtML](http://www.blog.cvbhg.cn/Article/details/064179.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/244492.sHtML](http://www.blog.cvbhg.cn/Article/details/244492.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/614390.sHtML](http://www.blog.cvbhg.cn/Article/details/614390.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/363919.sHtML](http://www.blog.cvbhg.cn/Article/details/363919.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/937132.sHtML](http://www.blog.cvbhg.cn/Article/details/937132.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/830498.sHtML](http://www.blog.cvbhg.cn/Article/details/830498.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/968736.sHtML](http://www.blog.cvbhg.cn/Article/details/968736.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/590023.sHtML](http://www.blog.cvbhg.cn/Article/details/590023.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/260925.sHtML](http://www.blog.cvbhg.cn/Article/details/260925.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/520558.sHtML](http://www.blog.cvbhg.cn/Article/details/520558.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/243988.sHtML](http://www.blog.cvbhg.cn/Article/details/243988.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/500201.sHtML](http://www.blog.cvbhg.cn/Article/details/500201.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/705051.sHtML](http://www.blog.cvbhg.cn/Article/details/705051.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/738959.sHtML](http://www.blog.cvbhg.cn/Article/details/738959.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/046057.sHtML](http://www.blog.cvbhg.cn/Article/details/046057.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/683452.sHtML](http://www.blog.cvbhg.cn/Article/details/683452.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/198256.sHtML](http://www.blog.cvbhg.cn/Article/details/198256.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/041836.sHtML](http://www.blog.cvbhg.cn/Article/details/041836.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/728992.sHtML](http://www.blog.cvbhg.cn/Article/details/728992.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/658998.sHtML](http://www.blog.cvbhg.cn/Article/details/658998.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/319637.sHtML](http://www.blog.cvbhg.cn/Article/details/319637.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/298512.sHtML](http://www.blog.cvbhg.cn/Article/details/298512.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/992585.sHtML](http://www.blog.cvbhg.cn/Article/details/992585.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/500820.sHtML](http://www.blog.cvbhg.cn/Article/details/500820.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/150217.sHtML](http://www.blog.cvbhg.cn/Article/details/150217.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/156549.sHtML](http://www.blog.cvbhg.cn/Article/details/156549.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/233167.sHtML](http://www.blog.cvbhg.cn/Article/details/233167.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/835404.sHtML](http://www.blog.cvbhg.cn/Article/details/835404.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/249485.sHtML](http://www.blog.cvbhg.cn/Article/details/249485.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/966351.sHtML](http://www.blog.cvbhg.cn/Article/details/966351.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/596128.sHtML](http://www.blog.cvbhg.cn/Article/details/596128.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/011136.sHtML](http://www.blog.cvbhg.cn/Article/details/011136.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/032620.sHtML](http://www.blog.cvbhg.cn/Article/details/032620.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/990258.sHtML](http://www.blog.cvbhg.cn/Article/details/990258.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/572478.sHtML](http://www.blog.cvbhg.cn/Article/details/572478.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/020897.sHtML](http://www.blog.cvbhg.cn/Article/details/020897.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/973867.sHtML](http://www.blog.cvbhg.cn/Article/details/973867.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/863891.sHtML](http://www.blog.cvbhg.cn/Article/details/863891.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/528796.sHtML](http://www.blog.cvbhg.cn/Article/details/528796.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/364409.sHtML](http://www.blog.cvbhg.cn/Article/details/364409.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/272951.sHtML](http://www.blog.cvbhg.cn/Article/details/272951.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/286574.sHtML](http://www.blog.cvbhg.cn/Article/details/286574.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/429401.sHtML](http://www.blog.cvbhg.cn/Article/details/429401.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/792336.sHtML](http://www.blog.cvbhg.cn/Article/details/792336.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/332433.sHtML](http://www.blog.cvbhg.cn/Article/details/332433.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/367283.sHtML](http://www.blog.cvbhg.cn/Article/details/367283.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/836853.sHtML](http://www.blog.cvbhg.cn/Article/details/836853.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/376478.sHtML](http://www.blog.cvbhg.cn/Article/details/376478.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/932678.sHtML](http://www.blog.cvbhg.cn/Article/details/932678.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/218669.sHtML](http://www.blog.cvbhg.cn/Article/details/218669.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/513471.sHtML](http://www.blog.cvbhg.cn/Article/details/513471.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/631283.sHtML](http://www.blog.cvbhg.cn/Article/details/631283.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/233067.sHtML](http://www.blog.cvbhg.cn/Article/details/233067.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/990979.sHtML](http://www.blog.cvbhg.cn/Article/details/990979.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/704646.sHtML](http://www.blog.cvbhg.cn/Article/details/704646.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/600566.sHtML](http://www.blog.cvbhg.cn/Article/details/600566.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/381492.sHtML](http://www.blog.cvbhg.cn/Article/details/381492.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/884789.sHtML](http://www.blog.cvbhg.cn/Article/details/884789.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/459252.sHtML](http://www.blog.cvbhg.cn/Article/details/459252.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/989830.sHtML](http://www.blog.cvbhg.cn/Article/details/989830.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/688097.sHtML](http://www.blog.cvbhg.cn/Article/details/688097.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/740251.sHtML](http://www.blog.cvbhg.cn/Article/details/740251.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/901594.sHtML](http://www.blog.cvbhg.cn/Article/details/901594.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/148834.sHtML](http://www.blog.cvbhg.cn/Article/details/148834.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/035567.sHtML](http://www.blog.cvbhg.cn/Article/details/035567.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/585559.sHtML](http://www.blog.cvbhg.cn/Article/details/585559.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/648466.sHtML](http://www.blog.cvbhg.cn/Article/details/648466.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/392222.sHtML](http://www.blog.cvbhg.cn/Article/details/392222.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/403414.sHtML](http://www.blog.cvbhg.cn/Article/details/403414.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/771919.sHtML](http://www.blog.cvbhg.cn/Article/details/771919.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/032433.sHtML](http://www.blog.cvbhg.cn/Article/details/032433.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/299354.sHtML](http://www.blog.cvbhg.cn/Article/details/299354.sHtML)
- [http://www.blog.cvbhg.cn/Article/details/229896.sHtML](http://www.blog.cvbhg.cn/Article/details/229896.sHtML)
