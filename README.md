# Update

fork的https://github.com/overtrue/chinese-calendar，修改五行的计算方式，修复每月最后一天23点的bug。

# Chinese calendar

:date: 中国农历（阴历）与阳历（公历）转换与查询工具

# Installing

```shell
$ composer require bedlate/chinese-calendar -vvv
```

# Usage

```php
use bedlate\ChineseCalendar\Calendar;

$calendar = new Calendar();

$result = $calendar->solar(2017, 5, 5); // 阳历
$result = $calendar->lunar(2017, 4, 10); // 阴历
$result = $calendar->solar(2017, 5, 5, 23) // 阳历，带 $hour 参数

```

结果：

```php
array (
  'lunar_year' => '2017',   // 农历年
  'lunar_month' => '04',    // 农历月
  'lunar_day' => '10',      // 农历日
  'lunar_hour' => NULL,     // 农历时
  'lunar_year_chinese' => '二零一七',  // (汉字)农历年
  'lunar_month_chinese' => '四月',    // (汉字)农历月
  'lunar_day_chinese' => '初十',      // (汉字)农历日
  'lunar_hour_chinese' => NULL,      // (汉字)农历时辰
  'ganzhi_year' => '丁酉',            // (干支)年柱
  'ganzhi_month' => '乙巳',           // (干支)月柱
  'ganzhi_day' => '壬辰',             // (干支)日柱
  'ganzhi_hour' => NULL,             // (干支)时柱
  'wuxing_year' => '火金',            // (五行)年
  'wuxing_month' => '木火',           // (五行)月
  'wuxing_day' => '水土',             // (五行)日
  'wuxing_hour' => NULL,             // (五行)时
  'color_year' => '红',              // (颜色)年
  'color_month' => '青',             // (颜色)月
  'color_day' => '黑',               // (颜色)日
  'color_hour' => NULL,              // (颜色)时
  'animal' => '鸡',                  // 生肖
  'term' => '立夏',                   // 节气
  'is_leap' => false,                // 是否闰月
  'gregorian_year' => '2017',   // 公历年
  'gregorian_month' => '05',    // 公历月
  'gregorian_day' => '05',      // 公历日
  'gregorian_hour' => NULL,     // 公历时
  'week_no' => 5,               // 星期数字
  'week_name' => '星期五',       // 星期汉子
  'is_today' => false,          // 是否今天
  'constellation' => '金牛',     // 星座
)

array (
  'lunar_year' => '2017',   // 农历年
  'lunar_month' => '04',    // 农历月
  'lunar_day' => '10',      // 农历日
  'lunar_hour' => '23',     // 农历时
  'lunar_year_chinese' => '二零一七',  // (汉字)农历年
  'lunar_month_chinese' => '四月',    // (汉字)农历月
  'lunar_day_chinese' => '初十',      // (汉字)农历日
  'lunar_hour_chinese' => '子时',     // (汉字)农历时辰
  'ganzhi_year' => '丁酉',            // (干支)年柱
  'ganzhi_month' => '乙巳',           // (干支)月柱
  'ganzhi_day' => '壬辰',             // (干支)日柱
  'ganzhi_hour' => '壬子',            // (干支)时柱
  'wuxing_year' => '火金',            // (五行)年
  'wuxing_month' => '木火',           // (五行)月
  'wuxing_day' => '水土',             // (五行)日
  'wuxing_hour' => '水水',            // (五行)时
  'color_year' => '红',              // (颜色)年
  'color_month' => '青',             // (颜色)月
  'color_day' => '黑',               // (颜色)日
  'color_hour' => '黑',              // (颜色)时
  'animal' => '鸡',                  // 生肖
  'term' => '立夏',                   // 节气
  'is_leap' => false,                // 是否闰月
  'gregorian_year' => '2017',   // 公历年
  'gregorian_month' => '05',    // 公历月
  'gregorian_day' => '05',      // 公历日
  'gregorian_hour' => '23',     // 公历时
  'week_no' => 5,               // 星期数字
  'week_name' => '星期五',       // 星期汉子
  'is_today' => false,          // 是否今天
  'constellation' => '金牛',     // 星座
)

```

> 你可能注意到，含时间的农历结果怎么是 `四月十一` 而不是 `四月初十`，具体见 #13

更多 API 请查看源码。

# Reference

- [1900年至2100年公历、农历互转Js代码 - 晶晶的博客](http://blog.jjonline.cn/userInterFace/173.html) - 数据与部分算法来源
- [中国历法 - 维基百科](https://zh.wikipedia.org/wiki/Category:%E4%B8%AD%E5%9B%BD%E5%8E%86%E6%B3%95)
- [农历 - 维基百科](https://zh.wikipedia.org/wiki/%E8%BE%B2%E6%9B%86)
- [阴历 - 维基百科](https://zh.wikipedia.org/wiki/%E9%98%B4%E5%8E%86)
- [阳历 - 维基百科](https://zh.wikipedia.org/wiki/%E9%98%B3%E5%8E%86)
- [干支 - 维基百科](https://zh.wikipedia.org/wiki/%E5%B9%B2%E6%94%AF)
- [星座 - 维基百科](https://zh.wikipedia.org/wiki/%E6%98%9F%E5%BA%A7)
- [生肖 - 维基百科](https://zh.wikipedia.org/wiki/%E7%94%9F%E8%82%96)

# License

MIT
