---
title: "[Algorithm] 숫자만 추출"
date: 2022-01-20 +0800
categories: [Algorithm]
tags: [java, algorithm, string]
---


### **Question**

- #### description

    문자와 숫자가 섞여있는 문자열이 주어지면 그 중 숫자만 추출하여 그 순서대로 자연수를 만듭니다.<br>
    만약 “tge0a1h205er”에서 숫자만 추출하면 0, 1, 2, 0, 5이고 이것을 자연수를 만들면 1205이 됩니다.<br>
    추출하여 만들어지는 자연수는 100,000,000을 넘지 않습니다.

- #### input
    첫 줄에 숫자가 썩인 문자열이 주어집니다. 문자열의 길이는 100을 넘지 않습니다.

- #### output
    첫 줄에 자연수를 출력합니다.


| | 예시값 |
| |:---:|
| 첫번째 입력 |`g0en2T0s8eSoft` |
| 출력 |    `208` |


### **Source**

```java
import java.util.Scanner;
import java.util.regex.Pattern;
public class Main {
  public static void main(String[] args){
           Scanner sc = new Scanner(System.in);
        String words = sc.nextLine();

        if(words.length() > 100) return;

        StringBuilder sb = new StringBuilder();

        for(int i=0; i < words.length(); i++){
            String word = String.valueOf(words.charAt(i));
            boolean numCheck = Pattern.matches("^[0-9]$", word);
            if(numCheck){
                sb.append(word);
            }
        }
        
        System.out.println(Integer.valueOf(sb.toString()));
  }
}
```

### **explanation**
...