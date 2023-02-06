### 898.Bitwise-ORs-of-Subarrays

本题的突破口在于，OR的结果不会特别多。任何一个元素作为左端点的时候，随着右端点的移动，OR的结果只会是单调地变大（某个bit的0变成1），因此最多只有32种可能。同理，以任何一个元素可以作为右端点，那么所有subarray的OR结果做多也是32种。

因此我们可以用类似背包问题的算法，穷举上一个元素为右端点时所有subarray的OR值，来更新该元素为右端点时所有subarray的OR值。

最终的答案是o(32N)数量级，因为可以全部存下来。