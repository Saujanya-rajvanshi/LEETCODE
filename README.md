# LEETCODE

- [leetcode](https://leetcode.com/)

## DSA
- [basic maths codes](#basic-maths-codes)
- [recursion](#recursion)
- [hashing](#hashing)

## Opperating System 
- [621. Task Scheduler](https://leetcode.com/problems/task-scheduler/) -[explanation](https://chatgpt.com/s/t_69db43196ce481918236fee67dd91454)


### hashing 

* [1. Two Sum](https://leetcode.com/problems/two-sum/)
* [217. Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)
* [219. Contains Duplicate II](https://leetcode.com/problems/contains-duplicate-ii/description/)
* [349. Intersection of Two Arrays](https://leetcode.com/problems/intersection-of-two-arrays/)
* [202. Happy Number](https://leetcode.com/problems/happy-number/description/)
* [128. Longest Consecutive Sequence]() ⭐
* [560. Subarray Sum Equals K]() ⭐
* [49. Group Anagrams]() ⭐
* [347. Top K Frequent Elements]()
* [3. Longest Substring Without Repeating Characters]()

## Intersection of Two Arrays

```cpp
class Solution {
public:
    vector<int> intersection(vector<int>& nums1, vector<int>& nums2) {
        unordered_set<int> s(nums1.begin(), nums1.end());
        vector<int> v;

        for(int x : nums2) {
            if(s.count(x)) {
                v.push_back(x);
                s.erase(x); // avoid duplicates
            }
        }
        return v;
    }
};
```
```cpp
class Solution {
public:
    vector<int> intersection(vector<int>& nums1, vector<int>& nums2) {
        unordered_set<int> s(nums1.begin(), nums1.end());
        unordered_set<int> res;

        for(int x : nums2) {
            if(s.count(x)) {
                res.insert(x);
            }
        }

        return vector<int>(res.begin(), res.end());
    }
};
```








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

- [20. Valid Parentheses](https://leetcode.com/problems/valid-parentheses/)
* [1021. Remove Outermost Parentheses](https://leetcode.com/problems/remove-outermost-parentheses/)
* [1903. Largest Odd Number in String](https://leetcode.com/problems/largest-odd-number-in-string/)
* [Longest Common Prefix](https://leetcode.com/problems/longest-common-prefix/)
* [Isomorphic Strings](https://leetcode.com/problems/isomorphic-strings/)
* [Rotate String](https://leetcode.com/problems/rotate-string/)
* [Valid Anagram](https://leetcode.com/problems/valid-anagram/)
* [Sort Characters By Frequency](https://leetcode.com/problems/sort-characters-by-frequency/)
* [Count Number of Substrings](https://leetcode.com/problems/count-substrings/)
* [387. First Unique Character in a String]()
* [383. Ransom Note]()
* [205. Isomorphic Strings]()
* [290. Word Pattern]()


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
- [3546. Equal Sum Grid Partition I](https://chatgpt.com/s/t_69c4058e503481919a321a9e750a33fa)
- [3548. Equal Sum Grid Partition II](https://leetcode.com/problems/equal-sum-grid-partition-ii/submissions/1959530630/?envType=daily-question&envId=2026-03-26)
- [2946. Matrix Similarity After Cyclic Shifts](https://leetcode.com/problems/matrix-similarity-after-cyclic-shifts/description/?envType=daily-question&envId=2026-03-27)
- [3474. Lexicographically Smallest Generated String](https://leetcode.com/problems/lexicographically-smallest-generated-string/submissions/1964426636/?envType=daily-question&envId=2026-03-31)
- [2839. Check if Strings Can be Made Equal With Operations I](https://leetcode.com/problems/check-if-strings-can-be-made-equal-with-operations-i/description/)
- [2840. Check if Strings Can be Made Equal With Operations II](https://leetcode.com/problems/check-if-strings-can-be-made-equal-with-operations-ii/description/)




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
- [326. Power of Three](https://leetcode.com/problems/power-of-three/description/) math / division
- [231. Power of Two](https://leetcode.com/problems/power-of-two/) bit / math
- [342. Power of Four](https://leetcode.com/problems/power-of-four/) math + bit
- [367. Valid Perfect Square](https://leetcode.com/problems/valid-perfect-square/) binary search / math
- [400. Nth Digit](https://leetcode.com/problems/nth-digit/) number pattern
- [172. Factorial Trailing Zeroes](https://leetcode.com/problems/factorial-trailing-zeroes/) count 5s
- [1006. clumsy factorial](https://leetcode.com/problems/clumsy-factorial/) simulation, stack / pattern
- [412. Fizz Buzz](https://leetcode.com/problems/fizz-buzz/) basic condition logic, modulo
- [1523. Count Odd Numbers in an Interval Range](https://leetcode.com/problems/count-odd-numbers-in-an-interval-range/) math formula, counting


### recursion 

* try to represent the problem in terms of index
* do all posible stuffs on that and index to that problem statment
* sum of all stuffs -> count ways
* min of all ways ->find min , for max -> max

- [9. Palindrome Number](https://leetcode.com/search/?q=palindrom+number+)
- [509. Fibonacci Number](https://leetcode.com/problems/fibonacci-number/)
- [231. Power of Two](https://leetcode.com/problems/power-of-two/)
- [70. Climbing Stairs](https://leetcode.com/problems/climbing-stairs/)
- [344. Reverse String](https://leetcode.com/problems/reverse-string/description/)


## Palindrome Number

```cpp
if (x < 0) return false;       
string s = to_string(x);
string rev = s;
reverse(rev.begin(), rev.end());
```

