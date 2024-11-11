# Maximize-Unique-Elements

You have an array A of size N. In a single operation, you can select any three elements from the array, remove them, and then out of these three integers, you discard the largest and smallest, reinserting the middle element back into the array. You continue performing this operation until all remaining elements in the array are unique. What is the maximum number of elements that can remain in the array after completing any number of operations (including potentially not performing any operations at all)?

from collections import Counter
import math

def solve(n, arr):

    freq = Counter(arr)
    

    unique_nums = len(freq)
    

    total_duplicates = n - unique_nums
    

    operations_needed = (total_duplicates + 1) // 2
    

    final_size = n - (operations_needed * 2)
    

    return min(unique_nums, final_size)


n = int(input())
arr = list(map(int, input().split()))


print(solve(n, arr))
