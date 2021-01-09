## 1. Reverse the words of a string without allocating extra space

✏️ Example:

```
today is a sunny day -> day sunny a is today
```

### 📝 Solution

Reverse the string blindly, then reverse the single words

✏️ Example:

```
                today is a sunny day

reverse:        yad ynnus a si yadot
reverse words:  day sunny a is today
```

## 2. Count the number of digits of the factorial of a big number

✏️ Example:

```
450! has 1001 digits
```

### 📝 Solution

The number of digits is given by `ceiling` the sum of the log10 of numbers from `1` to `N`.

✏️ Example:

```
450!
ceil(log10(1) + log10(2) + ... + log10(450)) = 1001
```

## 3. Given two arrays of numbers, find the only element which is missing from the second one

✏️ Example:

```
arr1 = [1, 6, 2, 3]
arr2 = [6, 1, 3]
answer = 2
```

#### 📝 Solutions

- Calculate the difference between the sums of both

✏️ Example:

```
arr1 = [1, 6, 2, 3]
sum1 = 1+6+2+3 = 12

arr2 = [6, 1, 3]
sum2 = 1+6+3 = 10

answer = 12 - 10 = 2
```

Since this solution can lead to integer overflow, the second one is recommended:

- Calculate the xor between the xor of both

✏️ Example:

```
arr1 = [1, 6, 2, 3]
xor1 = 1^6^2^3 = 6

arr2 = [6, 1, 3]
xor2 = 1^6^3 = 4

answer = 6 ^ 4 = 2
```

- Sort both and find the first mismatch

Another acceptable solution is to sort both the arrays and then linearly find the first mismatching pair.

✏️ Example:

```
arr1 = [1, 6, 2, 3]
sorted1 = [1, 2, 3, 6]

arr2 = [6, 1, 3]
sorted2 = [1, 3, 6]

[1, 1] OK
[2, 3] KO -> answer = 2
```
