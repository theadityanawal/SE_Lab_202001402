# Lab 7

## Name: Aditya Nawal

## Student ID: 202001402

# Section A

Based on the input ranges, we can identify the following equivalence classes:

1. **Valid dates**: The input triple (day, month, year) that represent a valid date in the Gregorian calendar, such as (3, 4, 1995).
2. **Invalid dates**: The input triple (day, month, year) that represent an invalid date, such as (31, 2, 2022) or (29, 2, 1900).
3. **Out of range dates**: The input triple (day, month, year) that are outside the allowed ranges, such as (0, 5, 2010) or (15, 13, 2005).
Based on these equivalence classes, we can design the following test cases:

### **Valid dates**

| Tester Action and Input Data | Expected Outcome |
| --- | --- |
| Calculate previous date for (15, 10, 2022) | 14, 10, 2022 |
| Calculate previous date for (1, 1, 2015) | 31, 12, 2014 |
| Calculate previous date for (31, 3, 2000) | 30, 3, 2000 |

### **Invalid dates:**

| Tester Action and Input Data | Expected Outcome |
| --- | --- |
| Calculate previous date for (29, 2, 2022) | Invalid date |
| Calculate previous date for (31, 4, 2010) | Invalid date |
| Calculate previous date for (30, 2, 2000) | Invalid date |

### **Out of range dates:**

| Tester Action and Input Data | Expected Outcome |
| --- | --- |
| Calculate previous date for (0, 5, 2010) | Invalid date |
| Calculate previous date for (15, 13, 2005) | Invalid date |
| Calculate previous date for (31, 12, 1899) | Invalid date |

### **Boundary Value Analysis:**

Using boundary value analysis, we can identify the following boundary test cases:

1. The earliest possible date: (1, 1, 1900)
2. The latest possible date: (31, 12, 2015)
3. The earliest day of each month: (1, 1, 2000), (1, 2, 2000), (1, 3, 2000),..., (1, 12, 2000)
4. The latest day of each month: (31, 1, 2000), (28, 2, 2000), (31, 3, 2000),..., (31, 12, 2000)
5. Leap year day: (29, 2, 2000)
6. Invalid leap year day: (29, 2, 1900)
7. One day before earliest date: (31, 12, 1899)
8. One day after latest date: (1, 1, 2016)

Based on these boundary test cases, we can design the following test cases:

### **Boundary Test Cases**

| Tester Action and Input Data | Expected Outcome |
| --- | --- |
| Calculate previous date for (1, 1, 1900) | Invalid date |
| Calculate previous date for (31, 12, 2015) | 30, 12, 2015 |
| Calculate previous date for (1, 1, 2000) | 31, 12, 1999 |
| Calculate previous date for (31, 1, 2000) | 30, 1, 2000 |
| Calculate previous date for (29, 2, 2000) | 28, 2, 2000 |
| Calculate previous date for (29, 2, 1900) | Invalid date |

## Program 1

The function `linearSearch` searches for a value v in an array of integers a. If v appears in the array a, then the function returns the first index `i`, such that `a[i] == v`; otherwise, -1 is returned.

```c
int linearSearch(int v, int a[]) {
	int i = 0;
	while (i < a.length) {
		if (a[i] == v) return(i);
		i++;
	}
	return (-1);
}
```

### **Equivalence Partitioning**

| Tester Action and Input Data | Expected Outcome |
| --- | --- |
| v is present in a | Index of v |
| v is not present in a | -1 |

### **Boundary Value Analysis**

| Tester Action and Input Data | Expected Outcome |
| --- | --- |
| Empty array a | -1 |
| v is present at the first index of a | 0 |
| v is present at the last index of a length of a | -1 |
| v is not present in a | -1 |

## Program 2

The function `countItem` returns the number of times a value v appears in an array of integers a.

```c
int countItem(int v, int a[]) {
	int count = 0;
	for (int i = 0; i < a.length; i++) {
		if (a[i] == v)
		count++;
	}
	return (count);
}
```

### **Equivalence Partitioning**

| Tester Action and Input Data | Expected Outcome |
| --- | --- |
| v is present in a | Number of times v appears in a |
| v is not present in a | 0 |

### **Boundary Value Analysis**

| Tester Action and Input Data | Expected Outcome |
| --- | --- |
| Empty array a | 0 |
| v is present once in a | 1 |
| v is present multiple times in a | Number of times v appears in a |
| v is present at the first index of a | 1 |
| v is present at the last index of a | 1 |
| v is not present in a | 0 |

## Program 3

The function `binarySearch` searches for a value v in an ordered array of integers a. If v appears in the array a, then the function returns an index `i`, such that `a[i] == v`; otherwise, `-1` is returned.
*Assumption: the elements in the array a are sorted in non-decreasing order.*

```c
int binarySearch(int v, int a[]) {
	int lo, mid, hi;
	lo = 0;
	hi = a.length-1;
	while (lo <= hi) {
		mid = (lo+hi)/2;
		if (v == a[mid]) return (mid);
		else if (v < a[mid]) hi = mid-1;
		else lo = mid+1;
	}
	return(-1);
}
```

### **Equivalence Partitioning**

| Tester Action and Input Data | Expected Outcome |
| --- | --- |
| v is present in a | Index of v |
| v is not present in a | -1 |

### **Boundary Value Analysis**

| Tester Action and Input Data | Expected Outcome |
| --- | --- |
| Empty array a | -1 |
| v is present at the first index of a | 0 |
| v is present at the last index of a length of a | -1 |
| v is not present in a | -1 |

## Program 4

The following problem has been adapted from *The Art of Software Testing, by G. Myers (1979).*
The function triangle takes three integer parameters that are interpreted as the lengths of the sides of a triangle. It returns whether the triangle is equilateral (three lengths equal), isosceles (two lengths equal), scalene (no lengths equal), or invalid (impossible lengths).

```c
final int EQUILATERAL = 0;
final int ISOSCELES = 1;
final int SCALENE = 2;
final int INVALID = 3;
int triangle(int a, int b, int c) {
	if (a >= b+c || b >= a+c || c >= a+b) return(INVALID);
	if (a == b && b == c) return(EQUILATERAL);
	if (a == b || a == c || b == c) return(ISOSCELES);
	return(SCALENE);
}
```

### **Equivalence Partitioning**

| Tester Action and Input Data | Expected Outcome |
| --- | --- |
| Invalid triangle (a+b<=c) | INVALID |
| Valid equilateral triangle (a=b=c) | EQUILATERAL |
| Valid isosceles triangle (a=b<c) | ISOSCELES |
| Valid scalene triangle (a<b<c) | SCALENE |

### **Boundary Value Analysis**

| Tester Action and Input Data | Expected Outcome |
| --- | --- |
| Invalid triangle (a+b<=c) | INVALID |
| Invalid triangle (a+c<b) | INVALID |
| Invalid triangle (b+c<a) | INVALID |
| Valid equilateral triangle (a=b=c) | EQUILATERAL |
| Valid isosceles triangle (a=b<c) | ISOSCELES |
| Valid isosceles triangle (a=c<b) | ISOSCELES |
| Valid isosceles triangle (b=c<a) | ISOSCELES |
| Valid scalene triangle (a<b<c) | SCALENE |

## Program 5

The function `prefix(String s1, String s2)` returns whether or not the `string s1` is a prefix of `string s2` (you may assume that neither s1 nor s2 is null).

```java
public static boolean prefix(String s1, String s2) {
	if (s1.length() > s2.length()) {
		return false;
	}
	for (int i = 0; i < s1.length(); i++) {
		if (s1.charAt(i) != s2.charAt(i)) {
			return false;
		}
	}
	return true;
}
```

### **Equivalence Partitioning**

| Tester Action and Input Data | Expected Outcome |
| --- | --- |
| Empty string s1 and s2 | True |
| Empty string s1 and non-empty s2 | True |
| Non-empty s1 is a prefix of non-empty s2 | True |
| Non-empty s1 is not a prefix of s2 | False |
| Non-empty s1 is longer than s2 | False |

### **Boundary Value Analysis**

| Tester Action and Input Data | Expected Outcome |
| --- | --- |
| Empty string s1 and s2 | True |
| Empty string s1 and non-empty s2 | True |
| Non-empty s1 is not a prefix of s2 | False |
| Non-empty s1 is longer than s2 | False |

## Program 6

Consider again the triangle classification program (P4) with a slightly different specification:

The program reads floating values from the standard input. The three values A, B, and C are interpreted as representing the lengths of the sides of a triangle. The program then prints a message to the standard output that states whether the triangle, if it can be formed, is scalene, isosceles, equilateral, or right angled.

Determine the following for the above program:

1. Identify the equivalence classes for the system
2. Identify test cases to cover the identified equivalence classes. Also, explicitly mention which test case would cover which equivalence class.
(Hint: you must need to be ensure that the identified set of test cases cover all identified equivalence classes)
3. For the boundary condition A + B > C case (scalene triangle), identify test cases to verify the boundary.
4. For the boundary condition A = C case (isosceles triangle), identify test cases to verify the boundary.
5. For the boundary condition A = B = C case (equilateral triangle), identify test cases to verify the boundary.
6. For the boundary condition A2 + B2 = C2 case (right-angle triangle), identify test cases to verify the boundary.
7. For the non-triangle case, identify test cases to explore the boundary.
8. For non-positive input, identify test points.

### Equivalence Classes

EC1: All sides are positive, real numbers.
EC2: One or more sides are negative or zero.
EC3: The sum of the lengths of any two sides is less than or equal to the length of the remaining side (impossible lengths).
EC4: The sum of the lengths of any two sides is greater than the length of the remaining side (possible lengths).

### Test cases

TC1 (EC1): A=3, B=4, C=5 (right-angled triangle)
TC2 (EC1): A=5, B=5, C=5 (equilateral triangle)
TC3 (EC1): A=5, B=6, C=7 (scalene triangle)
TC4 (EC1): A=5, B=5, C=7 (isosceles triangle)
TC5 (EC2): A=-2, B=4, C=5 (invalid input)
TC6 (EC2): A=0, B=4, C=5 (invalid input)

### Test cases for the boundary condition A + B > C

TC7 (EC4): A=2, B=3, C=6 (sum of A and B is equal to C)

### Test cases for the boundary condition A = C

TC8 (EC4): A=5, B=6, C=5 (A equals to C)

### Test cases for the boundary condition A = B = C

TC9 (EC4): A=1, B=1, C=1 (all sides are equal)

### Test cases for the boundary condition A^2 + B^2 = C^2

TC10 (EC4): A=3, B=4, C=5 (right-angled triangle)

### Test cases for the non-triangle case

TC11 (EC3): A=2, B=2, C=4 (sum of A and B is less than C)

### Test points for non-positive input

TP1 (EC2): A=0, B=4, C=5 (invalid input)
TP2 (EC2): A=-2, B=4, C=5 (invalid input)
Note: Test cases TC1 to TC10 covers all identified equivalence classes.

# Section B

## **Control flow diagram**

![https://user-images.githubusercontent.com/84441910/231426230-4f73e587-ef87-4d39-83df-3722a17df30d.png](https://user-images.githubusercontent.com/84441910/231426230-4f73e587-ef87-4d39-83df-3722a17df30d.png)

## **Test sets**

### Statement coverage test sets

To achieve statement coverage, we need to make sure that every statement in the code is executed at least once.

Test 1: p = empty vector
Test 2: p = vector with one point
Test 3: p = vector with two points with the same y component
Test 4: p = vector with two points with different y components
Test 5: p = vector with three or more points with different y components
Test 6: p = vector with three or more points with the same y component


### Branch coverage test sets

To achieve branch coverage, we need to make sure that every possible branch in the code is taken at least once

Test 1: p = empty vector
Test 2: p = vector with one point
Test 3: p = vector with two points with the same y component
Test 4: p = vector with two points with different y components
Test 5: p = vector with three or more points with different y components, and none of them have the same x component
Test 6: p = vector with three or more points with the same y component, and some of them have the same x component
Test 7: p = vector with three or more points with the same y component, and all of them have the same x component


### Basic condition coverage test sets

To achieve basic condition coverage, we need to make sure that every basic condition in the code (i.e., every Boolean subexpression) is evaluated as both true and false at least once

Test 1: p = empty vector
Test 2: p = vector with one point
Test 3: p = vector with two points with the same y component, and the first point has a smaller x component
Test 4: p = vector with two points with the same y component, and the second point has a smaller x component
Test 5: p = vector with two points with different y components
Test 6: p = vector with three or more points with different y components, and none of them have the same x component
Test 7: p = vector with three or more points with the same y component, and some of them have the same x component
Test 8: p = vector with three or more points with the same y component, and all of them have the same x component.
