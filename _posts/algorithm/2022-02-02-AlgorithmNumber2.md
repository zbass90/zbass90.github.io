---
title: "[Algorithm] 보이는 학생"
date: 2022-02-02 +0800
categories: [Algorithm]
tags: [java, algorithm, number]
---


### **Question**

- #### description

    선생님이 N명의 학생을 일렬로 세웠습니다. 일렬로 서 있는 학생의 키가 앞에서부터 순서대로 주어질 때,<br>
    맨 앞에 서 있는 선생님이 볼 수 있는 학생의 수를 구하는 프로그램을 작성하세요.<br>
    (앞에 서 있는 사람들보다 크면 보이고, 작거나 같으면 보이지 않습니다.)

- #### input
    첫 줄에 정수 N(5<=N<=100,000)이 입력된다. 그 다음줄에 N명의 학생의 키가 앞에서부터 순서대로 주어진다.

- #### output
    선생님이 볼 수 있는 최대학생수를 출력한다.


| | 예시값 |
| |:---:|
| 첫번째 입력 |`8` |
| 두번째 입력 | `130 135 148 140 145 150 150 153` |
| 출력 |`5` |


### **Source**

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.StringTokenizer;
  
public class Main {
  public static void main(String[] args) throws IOException {
   BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        int firstNum = Integer.parseInt(br.readLine());
        StringTokenizer secondNums = new StringTokenizer(br.readLine());

        StringBuffer sb = new StringBuffer();

        int[] intList = new int[firstNum];

        int cnt = 0;
        while(secondNums.hasMoreTokens()){
            intList[cnt++] = Integer.parseInt(secondNums.nextToken());
        }

        int maxNum = intList[0];
        int result = 1;
        for(int i=1; i < firstNum; i++){
            if(maxNum < intList[i]) {
                result++;
                maxNum = intList[i];
            }
        }

        System.out.println(result);
  }
}
```

### **explanation**
...