Kadane’s Algorithm in Python
Here, on this page, we will discuss the program for Kadane’s Algorithm in Python programming language

Kadane’s algorithm in Python

Problem Statement
 We are given an array and we need to find the largest contiguous subarray sum which can be done using Kadane’s algorithm efficiently.

Approach
 Kadane’s Algorithm can be viewed both as greedy and DP. As we can see that we are keeping a running sum of integers and when it becomes less than 0, we   reset it to 0 (Greedy Part). This is because continuing with a negative sum is way worse than restarting with a new range. Now it can also be viewed as a DP,   at each stage we have 2 choices: Either take the current element and continue with the previous sum OR restart a new range

Algorithm
Initialize a variable max_so_far and store maximum of the given array
Iterate using a for between 0 to length of array -1 by i
Initialize a variable s to store ith element of the array
Run a nested for loop using variable j from i+1 to length of array
Increment the value of s by arr[j]
Check if s is greater than max_so_far if true store s to max_so_far
After loop ends max_so_far stores the answer
Python Program for Kadane’s Algorithm
Python Code
Run
def fun(arr, l):
    max_so_far = max(arr)
    for i in range(l - 1):
        s = arr[i]
        for j in range(i + 1, l):
            s += arr[j]
            if s > max_so_far:
                max_so_far = s
    return max_so_far


array = [-2, -3, 4, -1, -2, 1, 5, -3]

print("Largest contiguous subarray sum is :", fun(array, len(array)))
Output
Largest contiguous subarray sum is : 7
