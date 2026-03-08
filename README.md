# LEETCODE

## questions solved

- [add digits](#add-digits)

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



