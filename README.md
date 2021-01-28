# SEO-better

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

