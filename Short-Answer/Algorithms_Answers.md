#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I

a)
When broken down each line is O(1). Yet the while loops has it run an undetermined amount of times. This makes a constant time turn into an O(n) time complexity. Without further information on the full algorithm we cannot determine if there is a worse time complexity so we must insist this snippet of algorithm is O(n).

b)
The first thought when seeing two loops in tandem is O(n^2). Then we must debate our instinct to make sure nothing in the algorithm stretches to a worse time complexity or better one. As we see each loop will run for each iteration it does conclude that this snippet of algorithm is O(n^2).

c)
Since bunnies can be any number and we are doing an operation on each bunny/number and not just picking one bunny/number we know that this is not constant time automatically. Because we are only using one operation the worst time complexity of this algorithm is O(n).


## Exercise II
Suppose that you have an n-story building and plenty of eggs. Suppose also that an egg gets broken if it is thrown off floor f or higher, and doesn't get broken if dropped off a floor less than floor f. Devise a strategy to determine the value of f such that the number of dropped + broken eggs is minimized.

Write out your proposed algorithm in plain English or pseudocode AND give the runtime complexity of your solution.

(parameter == floors) I would want to allow an input of floors
I would then set variables for the eggs amount and a dropped egg count and broken egg count.

Example:
``` python
def egg_drop(floors == 10):
 eggs = 50
 dropped_eggs = 0
 broken_eggs = 0
 ```

Then we must make a base case of dropped_eggs being less than eggs do the next process but at the same time stop when dropped_eggs equal eggs...

Example
```python
if dropped_eggs == eggs:
  return broken_eggs
 while dropped_eggs < eggs:
```

Now we must determine a floor at which an egg will be broken to minimize broken eggs we must go back and give a minimum floor so as not to throw errors if a user does not input a floor.... so to minimize broken eggs I would divide the number of floors in half and set eggs to break at half the half point + 1 floor because given an odd number of floors there may only be 1 more floor (such as 3 half would be 2nd plus one would be the third floor).

Example
```python
  f = floors // 2 + 1
    if floors >= f:
      dropped_eggs += 1
      broken_eggs += 1
    elif floors < f:
      dropped_eggs +=1
  return egg_drop(floors)
```
As a first pass solution I believe this will do the trick and then I would evaluate if there is a better runtime complexity than I have found. First I would assume this would be an O(n) solution because we are doing one operation on each floor which is an n number of floors. It would factor to O(2n) but we drop constants for O(n).


