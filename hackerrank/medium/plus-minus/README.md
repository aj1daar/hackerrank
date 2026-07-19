# Plus Minus

![Difficulty](https://img.shields.io/badge/Difficulty-Medium-yellow)

## Problem

Given an array of integers, calculate the ratios of its elements that are $positive$, $negative$, and $zero$. Print the decimal value of each fraction on a new line with 6 places after the decimal.

**Note:** This challenge introduces precision problems. The test cases are scaled to six decimal places, though answers with absolute error of up to $10^{-4}$ are acceptable.

**Example**  
$arr = [1,1,0,-1,-1]$  

There are $n=5$ elements: two positive, two negative and one zero.  Their ratios are $\frac{2}{5} = 0.400000$, $\frac{2}{5} = 0.400000$ and $\frac{1}{5} = 0.200000$.  Results are printed as:  

    0.400000
    0.400000
    0.200000
    
**Function Description**

Complete the $plusMinus$ function with the following parameter(s):

- $int\ arr[n]$: an array of integers

**Print**  
	Print the ratios of positive, negative and 	zero values in the array.  Each value should be printed on a separate line with $6$ digits after the decimal.  The function should not return a value.  

**Input Format**

The first line contains an integer, $n$, the size of the array.	 
The second line contains $n$ space-separated integers that describe $arr[n]$.

**Constraints**

$0 \lt n \le 100$  
$-100 \le arr[i] \le 100$  

**Output Format**

## Solution

**Language:** Java  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-07-19T16:25:10.227Z  

```java
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.function.*;
import java.util.regex.*;
import java.util.stream.*;
import static java.util.stream.Collectors.joining;
import static java.util.stream.Collectors.toList;

class Result {

    /*
     * Complete the 'plusMinus' function below.
     *
     * The function accepts INTEGER_ARRAY arr as parameter.
     */

    public static void plusMinus(List<Integer> arr) {
    // Write your code here
      float positives = 0;
        float negatives = 0;
        for (Integer i : arr){
            if (i.intValue() > 0) positives++;
            else if (i.intValue() < 0) negatives++; 
        }
        System.out.println(String.format("%.6f", (positives/arr.size())));
        System.out.println(String.format("%.6f", (negatives/arr.size())));
        System.out.println(String.format("%.6f", ((arr.size()-(positives+negatives))/arr.size())));

    }

}

public class Solution {
    public static void main(String[] args) throws IOException {
        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(System.in));

        int n = Integer.parseInt(bufferedReader.readLine().trim());

        List<Integer> arr = Stream.of(bufferedReader.readLine().replaceAll("\\s+$", "").split(" "))
            .map(Integer::parseInt)
            .collect(toList());

        Result.plusMinus(arr);

        bufferedReader.close();
    }
}

```

---

[View on HackerRank](https://www.hackerrank.com/challenges/plus-minus/problem)