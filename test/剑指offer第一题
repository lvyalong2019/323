package Chapter_02;

/**
 * 不修改数组找出重复的数字：
 * 在一个长度为n+1的数组里的所有数字都在1~n的范围内，所以数组中
 * 至少有一个数字是重复的。请找出数组中任意一个重复的数字，但不能
 * 修改输入的数组。例如，如果输入长度为8的数组｛2，3，5，4，3，2，6，7｝，
 * 那么对应的输出是重复的数字2或者3
 */

/**
 * 测试用例：
 * 有数字不在1~n的范围内（1 2 3 4）
 * 长度为n+1的数组里所有数字都在1~n的范围内（1 2 3 4 4 5 6 7 ）（2 3 5 4 3 2 6 7）
 * 无效输入测试用例（输入空数组）
 */

/**
 * 解法：
 * 二分解区间
 */

import java.util.ArrayList;
import java.util.Arrays;
import java.util.Scanner;

public class Test03Q2 {

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

    public static int duplicate(int numbers[],int length,int duplication) {

        for (int i = 0;i < length;i++){
            if(numbers[i] < 1 || numbers[i] > length - 1){
                System.out.println("输入数字不在规定范围内1");
                return duplication;
            }
        }

        int min = 1;
        int max = length-1;
        int temp = max;
        int sum = length;
        //若min到max区间内的数组长度超过区间长度，区间内必有重复值，将temp=max,max=(max+min)/2
        //否则，min=max,max=temp
        while (min != max || sum <= 1) {

            int lengthoftemp = max - min + 1;

            if (sum > lengthoftemp){
                temp = max;
                max = (min + max) / 2;
            }else {
                min = max + 1;
                max = temp;
            }

            sum = 0;
            for (int i = 0;i < length;i++){
                if (numbers[i] >= min && numbers[i] <= max)
                    sum++;
            }

            duplication = max;
        }

        return duplication;
    }

    public static int duplicate2(int numbers[],int length,int duplication) {

        for (int i = 0;i < length;i++){
            if(numbers[i] < 1 || numbers[i] > length - 1){
                System.out.println("输入数字不在规定范围内1");
                return duplication;
            }
        }

        int min = 1;
        int max = length-1;
        int middle = (min + max) / 2;
//        int sum = length;
        boolean flag = false;
        //若min到middle区间内的数组长度超过区间长度，区间内必有重复值，将max=middle,middle=(max+min)/2
        //否则，min=middle+1,middle=(max+min)/2
        while (max >= min){

            int lengthoftemp = middle - min + 1;

            int sum = 0;
            for (int i = 0;i < length;i++){
                if (numbers[i] >= min && numbers[i] <= middle)
                    sum++;
            }

            if (max == min && sum > 1){
                duplication = max;
                break;
            }

            if (sum > lengthoftemp){
                max = middle;
            }else {
                min = middle + 1;
            }
            middle = (max + min) / 2;

        }

        return duplication;
    }

}
