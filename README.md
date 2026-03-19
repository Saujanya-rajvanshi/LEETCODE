# LEETCODE

## questions solved

- [add digits](#add-digits)

## streaks questions

- [1980. find unique binary string](https://chatgpt.com/s/t_69ad3e966dc48191af5410b3d3608058)
- [3130. find all possible stable binary array ii](https://chatgpt.com/s/t_69b021b15d54819195784b507ebf560a)
- [1878. gets the biggest rohmbus sum](https://chatgpt.com/s/t_69b803f127d8819188553008dc509628)
- [1727. largest submatrix with rearrangment](https://chatgpt.com/s/t_69b9ed0cf6348191a49263b11d337d44)
- [3070. count submatrix with top left-element and sum less than k](https://chatgpt.com/s/t_69b9ee014e3c81918637a3cb9c5f18c2)
- [3212. Count Submatrices With Equal Frequency of X and Y](https://chatgpt.com/s/t_69bc10b88f2c81919d927e722c8cb5fb)

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



