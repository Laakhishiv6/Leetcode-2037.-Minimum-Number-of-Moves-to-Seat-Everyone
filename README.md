# Leetcode-2037.-Minimum-Number-of-Moves-to-Seat-Everyone
# Description
There are n availabe seats and n students standing in a room. You are given an array seats of length n, where seats[i] is the position of the ith seat. You are also given the array students of length n, where students[j] is the position of the jth student.

You may perform the following move any number of times:

Increase or decrease the position of the ith student by 1 (i.e., moving the ith student from position x to x + 1 or x - 1)
Return the minimum number of moves required to move each student to a seat such that no two students are in the same seat.

Note that there may be multiple seats or students in the same position at the beginning.
# Solution

Example 1:

Input: seats = [3,1,5], students = [2,7,4]

Output: 4

Explanation: The students are moved as follows:

- The first student is moved from position 2 to position 1 using 1 move.
- 
- The second student is moved from position 7 to position 5 using 2 moves.
- 
- The third student is moved from position 4 to position 3 using 1 move.
- 
In total, 1 + 2 + 1 = 4 moves were used.

Example 3:

Input: seats = [2,2,6,6], students = [1,3,2,6]

Output: 4

Explanation: Note that there are two seats at position 2 and two seats at position 6.

The students are moved as follows:

- The first student is moved from position 1 to position 2 using 1 move.
- 
- The second student is moved from position 3 to position 6 using 3 moves.
- 
- The third student is not moved.
- 
- The fourth student is not moved.
- 
In total, 1 + 3 + 0 + 0 = 4 moves were used.

1. Sorting step

Sorting ensures we align the smallest student position with the smallest seat position, the next smallest with the next seat, etc.

This minimizes unnecessary extra moves.

2. Pairing and summing moves

For each student–seat pair, we calculate the distance abs(seat - student) and add it to total moves.
# Algorithm
1. Create a total variable which will return the total number of differences of all the elements .
2. Sort seats array.
3. Sort students array.
4. Loop through the arrays and find the absolute difference bwtween the ith seat and ith student
5. Add the different to the total
6. Return total
# Code
class Solution:

    def minMovesToSeat(self, seats: List[int], students: List[int]) -> int:
        total=0
        seats_sorted=sorted(seats)
        students_sorted=sorted(students)
        for i in range(len(seats_sorted)):
                total+=abs((seats_sorted[i])-(students_sorted[i]))
        return total

