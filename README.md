<div align="center">
|              I              |           II           |           III           |           IV           |            V            |          
: | :--------------------------: | :-------------------: | :----------------------: | :---------------------: | :--------------: | :
| 数据结构与算法<br />[📝](#一数据结构与算法) | Java<br/>[☕️](#二java) | 操作系统<br />[💻](#三操作系统) | 数据库<br />[💾](#四数据库) | 网络<br/>[☁️](#五网络) |
</div>

## 解题思路

要求时间复杂度 O(N)，空间复杂度 O(1)。因此不能使用排序的方法，也不能使用额外的标记数组。

对于这种数组元素在 [0, n-1] 范围内的问题，可以将值为 i 的元素调整到第 i 个位置上进行求解。

以 (2, 3, 1, 0, 2, 5) 为例，遍历到位置 4 时，该位置上的数为 2，但是第 2 个位置上已经有一个 2 的值了，因此可以知道 2 重复：

<div align="center"> <img src="pics/49d2adc1-b28a-44bf-babb-d44993f4a2e3.gif" width="250px"> </div><br>


```
public boolean duplicate(int[] nums, int length, int[] duplication) {
    if (nums == null || length <= 0)
        return false;
    for (int i = 0; i < length; i++) {
        while (nums[i] != i) {
            if (nums[i] == nums[nums[i]]) {
                duplication[0] = nums[i];
                return true;
            }
            swap(nums, i, nums[i]);
        }
    }
    return false;
}

private void swap(int[] nums, int i, int j) {
    int t = nums[i];
    nums[i] = nums[j];
    nums[j] = t;
}
```
```java
public static void main(String[] args) throws Exception {
        Scanner in = new Scanner(System.in);

        System.out.println("请输入长度为n+1的数组，所有数字都在1~n的范围内");
        String a = in.nextLine();
        if(a.isEmpty()){
            System.out.println("输入数组为空");
            System.exit(1);
        }

        String [] b = a.split(" ");
        int length =b.length;
        int [] c = new int[length];
        for (int i = 0;i < length;i++)
            c[i] = Integer.valueOf(b[i]);

        int duplication = 0;
        duplication = duplicate2(c,length,duplication);
        if (duplication != 0)
            System.out.println(duplication);
    }
```

### 一数据结构与算法

[解题思路](https://github.com/lvyalong2019/323/blob/master/test/%E5%89%91%E6%8C%87offer%E7%AC%AC%E4%B8%80%E9%A2%98.md#%E8%A7%A3%E9%A2%98%E6%80%9D%E8%B7%AF)

