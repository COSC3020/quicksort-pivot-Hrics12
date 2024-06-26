[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/IF3rQO50)
# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.


I believe the Median-of-three is a the better choice for a pivot. You are looking at more elements then selecting the first one.
If you have $n$ elements then picking the first element would give you $1/n$ probability that you picked a good pivot.
With the median-of-three the probability would be higher because if the array is randomly sorted then the median of the first, middle, and last
elements are more likely to be near the middle then just the first element. Thee median-of-three takes into accout more info of the distripution of the data. When you chose the first element you're not considering any info about the rest of the array.

Well assuming the "good" pivot is the center of the array then choosing the first, middle and last elements would give you a probability that the median is in the middle, then 50% of the sorted array is higher.

If the array is randomly ordered then each of the three elements is equally likely to be the smallest, middle, or largest of the three. The probability that the median of these three elements is in the middle 50% of the sorted array is 1 because the median of three numbers is always in the middle 50% of those numbers.

Considering the first, middle, and last elements of an array of size $n$ there are $n!$ possible permutations of the array. But for any given permutation there are six possible orderings of these three specific elements. In four out of these six orderings the median falls within the middle 50% of the sorted array So, the probability of choosing a "good" pivot with the median-of-three method is 4/6, or about 67%. This is better the the 50% probability when choosing the first element as the pivot. If the data is nearly sorted, both picking the first element and median of 3 might not be the best in quicksort because they both could produce very imbalanced partitions. But with the data being randomly then median of 3 is the way to go.
https://stackoverflow.com/questions/25294319/in-quicksort-if-an-array-is-randomized-does-using-the-median-of-3-for-pivot-sel
