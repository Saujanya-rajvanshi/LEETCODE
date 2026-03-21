# LEETCODE

## questions solved


### basic maths codes 
- [1006. clumsy factorial](https://leetcode.com/problems/clumsy-factorial/submissions/1953926003/)
- [9. palindrom number](https://leetcode.com/problems/palindrome-number/description/)
- [258. Add Digits](https://leetcode.com/problems/add-digits/description/)
- [412. Fizz Buzz](https://leetcode.com/problems/fizz-buzz/)
- [1523. Count Odd Numbers in an Interval Range](https://leetcode.com/problems/count-odd-numbers-in-an-interval-range/description/)
- [231. Power of Two](https://leetcode.com/problems/power-of-two/description/)
- [326. Power of Three](https://leetcode.com/problems/power-of-three/description/)
- [69. Sqrt(x)](https://leetcode.com/problems/sqrtx/submissions/1954434965/)
- [202. Happy Number](https://leetcode.com/problems/happy-number/description/)
- [35. Search Insert Position](https://leetcode.com/problems/search-insert-position/description/)




### recursion 

### hashing 

### sorting 
- [75. sort colors](https://leetcode.com/problems/sort-colors/description/)

### searching 

### arrays 
- [1. two sum](https://leetcode.com/problems/two-sum/description/)


### binary search
- [704. binary search](https://leetcode.com/problems/binary-search/description/)

### string


## streaks questions

- [1980. find unique binary string](https://chatgpt.com/s/t_69ad3e966dc48191af5410b3d3608058)
- [3130. find all possible stable binary array ii](https://chatgpt.com/s/t_69b021b15d54819195784b507ebf560a)
- [1878. gets the biggest rohmbus sum](https://chatgpt.com/s/t_69b803f127d8819188553008dc509628)
- [1727. largest submatrix with rearrangment](https://chatgpt.com/s/t_69b9ed0cf6348191a49263b11d337d44)
- [3070. count submatrix with top left-element and sum less than k](https://chatgpt.com/s/t_69b9ee014e3c81918637a3cb9c5f18c2)
- [3212. Count Submatrices With Equal Frequency of X and Y](https://chatgpt.com/s/t_69bc10b88f2c81919d927e722c8cb5fb)
- [3567. Minimum Absolute Difference in Sliding Submatrix](https://chatgpt.com/s/t_69bd5f2ba50c81918ca7a8b0c46ace83)
- [3643. Flip Square Submatrix Vertically](https://chatgpt.com/s/t_69be6658ba94819189db2b37c201ca07)


### add digits 
```cpp
int addDigits(int num) {
        while(num >= 10){ 
            int n = num ;
            int sum = 0 ;
            while(n != 0){
                int dig = n % 10;
                n = n / 10;
                sum += dig ; 
            }
            num = sum ;    
        }
    return num ;
}
```

#### We can optimize this using the Digital Root property

The repeated sum of digits of a number (its digital root) is determined by the number modulo 9, which causes the result to repeat in a cycle of 1 through 9.

```cpp
int addDigits(int num) {
    if(num == 0) return 0;   // 1 + (-1 % 9) so, handling 0 here
    return 1 + (num - 1) % 9;  //(num - 1) is adjustting the multiple of 9 , 1 + (567) % 9 gives 0 , 1 + (567 - 1) % 9 gines 1 + 8 = 9
}
```

💡**Fun fact :**
* This property is used in error detection in ancient math called "casting out nines.
* it’s a quick verification trick, not a proof.
* works for addition, subtraction, and multiplication because all of them preserve the mod 9 property.
- [example](https://chatgpt.com/s/t_69ad3acc5bb0819180638bac59a3a53b)



