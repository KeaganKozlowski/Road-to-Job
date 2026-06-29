# Brute Force `O(n^2)`

```
FUNCTION twoSum(nums, target):
    FOR i FROM 0 TO length of nums - 1:
        FOR j FROM 0 TO length of nums - 1:
            IF i IS NOT EQUAL TO j:
                IF nums[i] + nums[j] EQUALS target:
                    RETURN [i, j]
                    
    RETURN []
```

## Explanation

This approach works by checking every possible combination of two numbers in the array until it finds a pair that adds up to the target.

Step-by-Step Logic:
1. The Outer Loop (i): Picks the first number in the pair. It starts at the beginning of the array and moves forward one by one.
2. The Inner Loop (j): Picks the second number in the pair. For every single number chosen by i, j scans through the entire array.
3. The Guard Rail (i != j): This checks to make sure the algorithm isn't adding a number to itself (e.g., using the element at index 0 twice).
4. The Match: It checks if nums[i] + nums[j] == target. If it matches, it immediately returns those two indices and stops.

Why it's slow:
Imagine you have an array of 1,000 numbers. The outer loop runs 1,000 times, and for each of those times, the inner loop runs 1,000 times. That is $1,000 \times 1,000 = 1,000,000$ operations.

# Hash table `O(n)`

```
FUNCTION twoSum(nums, target):
    CREATE an empty map called 'seen'

    FOR each 'index' and 'current_number' in 'nums':
        CALCULATE complement = target - current_number

        IF complement EXISTS in 'seen':
            RETURN [seen[complement], index]

        STORE 'current_number' as key and 'index' as value in 'seen'

    RETURN []
```

## Explanation

Instead of looking forward and checking every pair, this approach looks backward at numbers it has already seen. It uses a Hash Map (or Dictionary) to remember past numbers and where they were located.

Step-by-Step Logic:
1. The Core Concept (The Complement): If you are looking at a number (num) and trying to reach target, you know exactly what other number you need. That required number is the complement ($target - num$).Example: If your target is 9 and your current number is 2, you know you need a 7 ($9 - 2 = 7$).
2. The Single Pass: The algorithm loops through the array exactly once.
3. The Memory Check: At each number, it calculates the complement and asks the Hash Map: "Have we seen this complement before?"If Yes: You found the pair! Return the index of the complement (stored in the map) and the current index.If No: Store the current number and its index in the Hash Map so future numbers can look it up, then move to the next item.

Why it's fast:
Because Hash Map lookups take constant time ($O(1)$), checking if the complement exists is nearly instantaneous. If you have 1,000 numbers, the loop only runs 1,000 times total. It trades a tiny bit of computer memory (to hold the map) for massive time savings.