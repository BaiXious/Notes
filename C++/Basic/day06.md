##remove_if

关于remove_if/remove 移除性算法来说，是根据元素值或某一准则，在一个区间内移除某些元素。这些算法并不能改变元素的数量，它们只是以逻辑上的思考，将原本置于后面的“不移除元素”向前移动，

覆盖那些被移除元素而已，它们都返回新区间的逻辑终点（也就是最后一个“不移除元素”的下一位置）。

ForwardIt remove( ForwardIt first, ForwardIt last, const T& value );// Removes all elements that are equal to value.

ForwardIt remove_if( ForwardIt first, ForwardIt last, UnaryPredicate p );//Removes all elements for which predicate p returns true.

返回的是变动后的序列的新逻辑终点，也就是最后一个未被移除的元素的下一个位置。
未被移除的元素在相对次序上保持不变。
调用者在调用此算法之后，应保证从此采用返回的新逻辑终点，而不再使用原始终点end；
