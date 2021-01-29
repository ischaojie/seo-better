# SEO-Better

参考：
google 站长指南

### 网址

- 保持网址结构简单，容易阅读。

  good:

  ```
  https://www.example.com/hotel/beijing
  ```

  bad:

  ```
  http://www.example.com/hotel？id_sezione=360&id=3a5ebc944f41daa6f849f
  ```

- 在网址中使用连字符，不要用下划线。

  good:

  ```
  https://www.example.com/hero-shiniao
  ```

  bad:

  ```
  https://www.example.com/hero_shiniao
  ```

- 尽可能避免在网址中使用会话 ID，而应考虑使用 Cookie。
  good：
  ```
  https://www.example.com/user/shiniao
  ```
  bad:
  ```
  https://www.example.com/user/3a5ebc944f41daa6f849f
  ```
- 因规则（比如排序、时间）产生的网址应该在 rebot.txt 中阻止。

  good:

  ```
  http://www.example.com/hotel-search-results.jsp
  ```

  bad:

  ```
  # 特价酒店
  http://www.example.com/hotel-search-results.jsp?Ne=292&N=461
  # 特价海景酒店
  http://www.example.com/hotel-search-results.jsp?Ne=292&N=461+4294967240
  # 带健身中心的特价海景酒店
  http://www.example.com/hotel-search-results.jsp?Ne=292&N=461+4294967240+4294967270
  ```

  搜索引擎只需要知道特价酒店列表即可，而不是所有的搜索条件。添加上述网址规则到 rebot.txt。

### 网站链接

- 对于出站链接，在 `<a>` 标记中使用 `rel` 属性，表明网站与链接页之间的关系，比如广告。对于那些无需说明用意、允许直接跟踪的常规链接，无需添加 rel 属性。

  good:

  对于广告链接，或者付费展示位，使用 `rel="sponsored"`，

  ```
  <a href="https://horses.example.com/Palomino" rel="sponsored">
  ```

  对于用户生成的内容的链接标记为 ugc。

  ```
  <a href="https://www.example.com/comment" rel="ugc">
  ```

- 确保链接可供抓取。

  good:

  ```
  <a href="https://example.com">
  ```

  bad:

  ```
  <a routerLink="some/path">

  # 爬虫无法向该链接发送请求
  <a onclick="goto('https://example.com')">

  <span href="https://example.com">

  # 不要使用空链接
  <a href="#">

  # 或者把链接放在 JavaScript 中
  javascript:window.location.href='/products'
  ```

### 图片

- 图片名应该表明图片主题，同时应该有代替文本（如果无法看到图片）。

  bad:

  ```
  # 不要使用无意义的图片名
  <img src="IMG00023.jpg"/>

  # 不要在 alt 中堆砌关键字
  <img src="puppy.jpg" alt="puppy dog baby dog pup pups puppies doggies pups litter puppies dog retriever"/>
  ```

  good:
  ```
  <img src="puppy.jpg"/>
  ```

  better:

  ```
   <img src="puppy.jpg" alt="Dalmatian puppy playing fetch"/>
  ```

- 不要使用 css 展示图片

    bad:
    ```
    <div style="background-image:url(puppy.jpg)">A golden retriever puppy</div>
    ```
    good:
    ```
    <img src="puppy.jpg" alt="A golden retriever puppy" />
    ```
