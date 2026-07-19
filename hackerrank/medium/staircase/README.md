# Plus Minus

![Difficulty](https://img.shields.io/badge/Difficulty-Medium-yellow)

## Problem

Staircase detail

This is a staircase of size $n = 4$:

	   #
	  ##
	 ###
	####

Its base and height are both equal to $n$.  It is drawn using `#` symbols and spaces. **The last line is not preceded by any spaces.** 

Write a program that prints a staircase of size $n$.  

**Function Description**

Complete the $staircase$ function with the following parameter(s):  

- $int\ n$: an integer  

**Print**  

Print a staircase as described above. No value should be returned.  
**Note**: The last line is not preceded by spaces. All lines are right-aligned.

**Input Format**

A single integer, $n$, denoting the size of the staircase.

**Constraints**

$0 \lt n \le 100$ .  

**Output Format**

## Solution

**Language:** Java  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-07-19T16:25:52.662Z  

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

[View on HackerRank](https://www.hackerrank.com/challenges/staircase/problem)