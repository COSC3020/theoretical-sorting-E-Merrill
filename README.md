# Theoretical Sorting

A Computer Science researcher claims to have come up with a sorting algorithm
that can sort arbitrary elements in $O(n)$ time based on comparisons of two
elements at a time. This would be asymptotically faster than any known general
sorting algorithm. The algorithm itself is proprietary and will be sold by a
company.

**How would you verify this claim? You may assume that you have access to a
black-box implementation of the sorting algorithm, i.e. you cannot examine the
source code, but you can use it to sort any list you like. Explain in detail
your method for investigating whether X is correct, including any expected
results you would get.**

To verify the claim, I would create a reverse sorted list (which tends to be the worst case for most sorting algorithms) of some arbitrary size, and run the sort on it, while timing how long the algorithm takes. Then, once that sort is completed, I would do the same thing, but with the list having a size 10 times larger than the initial size I tested, still timing how long the algorithm takes. If the algorithm is truly linear, then the second sort will only increase tenfold, as opposed to $n log(n)$ or $n^2$    Then, I would test it once more, with a reverse sorted list that is 10 times larger than the list used in the second trial, again keeping track of the time. Once again, I would expect the alogrithm to only take 10 times as long, since the assumption is that it is linear. Depending on if the results are still trivial, I would continue until the input size would have to have an affect on something sorting in linear time (i.e. 10,000,000 elements or more, assuming the computer could handle it.) Additionally, I would make sure that each trial was done on the same computer, with as little background processes as can be. I would also ensure that the cooling system and memory for the computer are good enough that they actually serve their purpose effectively. This is to ensure as little outside influence is affecting the runtime as possible. Truthfully, the tests could be done on a raspberry pi, jsut with smaller input sizes, and with the expectation that they would take quite some time to complete (though that probably wouldn't yield the most accurate results.) Then, looking at all the times I gathered, I would be able to determine if the algorithm was linear or not. If it was linear, then each increase in list size would increase runtime by roughly 10 times. If the increase in runtime is noticably different from a simple 10x, then I would know that the algorithm was not sorting in linear time complexity. 

**Also give a theoretical argument for why X could or could not be correct, based
on the complexity of the general sorting problem we covered in class.**

X could not be correct in the assertion that the algorithm is sorting in linear time. As we figured out in class, a linear sort is possible when we have additional knowledge/constraints that make the sorting easier, such as limited to numbers 1-5 or five different colors (aka bucket sort.) However, this sorting algorithm was said to be able to sort *arbitrary* elements, meaning it does not matter what they are, so they can be anything. The elements can be totally randomized, and it wouldn't matter to the algorithm. This algorithm behave similar to the decision tree sorting algorithm we discussed in class, which compares two elements, and then makes a decision based on the outcome of the comparison. However, even with that algorithm, the complexity would end up being $log(n!) = n log(n)$, which is still slower than linear. So, this theoretical algorithm is jsut comparing two elements with each other, and there is no prior knowledge of the elements to make something like bucket sort possible. As such, it is not possible for it to sort in linear time. 

Add your answers to this markdown file.


I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.
