## remove_if

关于remove_if/remove 移除性算法来说，是根据元素值或某一准则，在一个区间内移除某些元素。这些算法并不能改变元素的数量，它们只是以逻辑上的思考，将原本置于后面的“不移除元素”向前移动，

覆盖那些被移除元素而已，它们都返回新区间的逻辑终点（也就是最后一个“不移除元素”的下一位置）。

ForwardIt remove( ForwardIt first, ForwardIt last, const T& value );// Removes all elements that are equal to value.

ForwardIt remove_if( ForwardIt first, ForwardIt last, UnaryPredicate p );//Removes all elements for which predicate p returns true.

+ 返回的是变动后的序列的新逻辑终点，也就是最后一个未被移除的元素的下一个位置。
+ 未被移除的元素在相对次序上保持不变。
+ 调用者在调用此算法之后，应保证从此采用返回的新逻辑终点，而不再使用原始终点end；

remove_if的函数原型如下：
```cpp
template<class ForwardIt, class UnaryPredicate>
ForwardIt remove_if(ForwardIt first, ForwardIt last, UnaryPredicate p)
{
    first = std::find_if(first, last, p);
    if (first != last)
        for(ForwardIt i = first; ++i != last; )
            if (!p(*i))
                *first++ = std::move(*i);
    return first;
}
```
remove_if在头文件algorithm中，故要使用此函数，需添加#include <algorithm>

由于remove_if函数的参数是迭代器，通过迭代器无法得到容器本身，
而要删除容器内的元素必须通过容器的成员函数来进行。
因而此函数无法真正删除元素，只能把要删除的元素移到容器末尾并返回要被删除元素的迭代器，
然后通过erase成员函数来真正删除。因为一般remove_if和erase函数是成对出现的。
