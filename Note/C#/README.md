## Type
- [ValueTuple](https://dotblogs.com.tw/ASPNETShare/2017/02/24/20170223-ValueTuple)
> ValueTuple 是 value type，所以它使用的記憶體空間使用在 program stack，因此使用不會有 garbage collection

- [C# 4.0：Covariance 與 Contravariance 觀念入門](https://www.huanlintalk.com/2009/10/c-40covariance-and-contravariance.html)

## System
- [工作十余年，还是一直被问 委托和事件 有什么区别？ 真是够了](https://zhuanlan.zhihu.com/p/178307774)

## Collection
- [C# 回傳內部資料集合的幾種方式，考慮封裝與設計需求](https://dev.twsiyuan.com/2018/02/encapsulating-list-collection-in-c-sharp.html)
- [Iterate over two collections of equal length](https://codereview.stackexchange.com/questions/48661/iterate-over-two-collections-of-equal-length)
```sh
foreach (var (cell, id) in cells.Zip(randomizedIDs, (key, value) => (Cell: key, ID: value)))
{
    idDict[cell] = id;
    cell.selectCallback = Select;
}
```

- Random
```sh
var random_list = list.OrderBy(i => Guid.NewGuid()).ToList();
```

## Format
- [內插字串](https://dotblogs.com.tw/lazycodestyle/2016/06/24/005827)
