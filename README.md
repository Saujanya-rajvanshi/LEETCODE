# LEETCODE

## questions solved


### basic maths codes 
- [7. Reverse Integer](https://leetcode.com/problems/reverse-integer/)  digit extraction
- [9. palindrom number](https://leetcode.com/problems/palindrome-number/) reverse / compare
- [66. Plus One](https://leetcode.com/problems/plus-one/) carry handling
- [69. Sqrt(x)](https://leetcode.com/problems/sqrtx/) basic math / binary search
- [50. Pow(x, n)](https://leetcode.com/problems/powx-n/description/) fast exponentiation
- [258. Add Digits](https://leetcode.com/problems/add-digits/) digit sum / math trick
- [202. Happy Number](https://leetcode.com/problems/happy-number/)  digit square sum
- [263. Ugly Number](https://leetcode.com/problems/ugly-number/)  prime factor check (2,3,5)
- [204. Count Primes]() sieve of eratosthenes
- [326. Power of Three]() math / division
- [231. Power of Two]() bit / math
- [342. Power of Four]() math + bit
- [367. Valid Perfect Square]() binary search / math
- [400. Nth Digit]() number pattern
- [172. Factorial Trailing Zeroes]() count 5s
- [1006. clumsy factorial](https://leetcode.com/problems/clumsy-factorial/)
- [258. Add Digits](https://leetcode.com/problems/add-digits/) 
- [412. Fizz Buzz](https://leetcode.com/problems/fizz-buzz/)
- [1523. Count Odd Numbers in an Interval Range](https://leetcode.com/problems/count-odd-numbers-in-an-interval-range/)
- [231. Power of Two](https://leetcode.com/problems/power-of-two/)
- [326. Power of Three](https://leetcode.com/problems/power-of-three/)
- [202. Happy Number](https://leetcode.com/problems/happy-number/)


## importants

### digit extraction : 
```
digit = x % 10
x = x / 10
rev = rev * 10 + digit
```

### if overflow
1. You are building a number digit by digit
2. The problem has a range constraint
3. You are using only int (32-bit)

add this :
```
if(rev > INT_MAX/10 || rev < INT_MIN/10) return 0;
```

## reversing an number by making string 
```
string s = to_string(x);
string rev = s;
reverse(rev.begin(), rev.end());
```

## carry handling
```
digits.insert(digits.begin(), 1);
```

## sqrt
```
int i = 1;
while(i <= x / i){
    i++;
}
```

## pow x,n 

```
class Solution {
public:
    double myPow(double x, int n) {
        if(n == 0) return 1;

        double real = x;

        long long a = n;
        if(n < 0){
            n = -n;
        }
        for(int i = 1; i < n ;i++){
            x = real*x;
        }
        if(a < 0){
            return 1/x;
        }
    return x;
    }
};
```
```
class Solution {
public:
    double myPow(double x, int n) {

        long long pow = n;

        if(pow < 0){
            x = 1/x;
            pow = -pow;
        }

        double ans = 1;

        for(int i = 0; i < pow ;i++){
            ans *= x;
        }
        
    return ans;
    }
};
```

```cpp
class Solution {
public:
    double myPow(double x, int n) {

        long long pow = n;

        if(pow < 0){
            x = 1/x;
            pow = -pow;
        }

        double ans = 1;

        while(pow > 0){
            if(pow % 2 == 1){   // odd
                ans *= x;
            }
            x *= x;            // square
            pow /= 2;
        }
        
    return ans;
    }
};
```

## add digit 

use modulo nine work foe addition , mul etc
```cpp
        if(num == 0) return 0;   
        return 1 + (num - 1) % 9; 
```

## digit square sum

repeatedly transform number,  <br>
Two possibilities: <br>
reaches 1 → happy number <br>
enters a cycle (loop) → never reaches 1 <- use set <br>

```
while(n != 1 && seen.find(n) == seen.end()) // Keep going until we reach 1 (happy number) && n is not in the set yet
```

## Ugly Number,  prime factor check (2,3,5)

```cpp
        while(n % 2 == 0) n /= 2;
        while(n % 3 == 0) n /= 3;
        while(n % 5 == 0) n /= 5;

        return n == 1;
```













### recursion 

### hashing 

### sorting 
- [75. sort colors](https://leetcode.com/problems/sort-colors/description/)

### searching 

### arrays 
- [1. two sum](https://leetcode.com/problems/two-sum/description/)


### binary search
- [704. binary search](https://leetcode.com/problems/binary-search/description/)
- [69. Sqrt(x)](https://leetcode.com/problems/sqrtx/submissions/1954434965/)
- [35. Search Insert Position](https://leetcode.com/problems/search-insert-position/description/)


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
- [1886. Determine Whether Matrix Can Be Obtained By Rotation](https://chatgpt.com/s/t_69bfc45d620c8191a6fe190131d2dcac)
- [1594. Maximum Non Negative Product in a Matrix](https://chatgpt.com/s/t_69c08d2db74c8191ac5a8ac6f04970b5)
- [2906. Construct Product Matrix](https://chatgpt.com/s/t_69c1db28a25c8191b9b3fb657810728c)






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



