# Compsci Note April 7th
### Data Structures and Algorithms
Big O Notation

Gives an upper bound of the complexity in the worst case, helping to quantify performance as the input size becomes arbitrarily large.

The size of the input complexities ordered in from smallest to largest - n


Algorithm Analysis
To analyze how runtime of an algorithm scales as the input size increases to infinity

o(1)
o(n)
o(n^2)
**Big O notation** is used in Computer Science to describe the performance or complexity of an algorithm.
* As for a single algorithm, we use Big O notation to **categorize or classify** the growth rate function of algorithms as input size goes to infinity.
* Given two algorithms, define their runtime functions of input size N based on the frequency of basic operations and measure their growth order by their growth rate: **faster growth rate (namely faster percentage runtime growth according to input size going to infinity) corresponds to higher growth order.** The growth order is also called asymptotic order. For example, T(N) = N2, F(N) = Nlog2N, F(N) has higher asymptotic order than T(N).
* In Big O notation, all functions that have the same **growth rate when input size goes to infinity** (as determined by the highest order term of the function) are characterized using the same Big O notation. It is an approximate concept, and we care about the growth scalability according to input size.
* Given a function that describes the running time of an algorithm, the Big O notation for that function can be determined using the following rules:
    * If f(x) is a sum of several terms, the highest order term (the one with the fastest growth rate) is kept and others are discarded.
    * If f(x) has a term that is a product of several factors, all constants (those that are not in terms of x) are omitted.
    * Given an algorithm, guideline for general algorithmic time complexity analysis is as follows:
        * Decide on parameter of runtime growth function, N, indicating input size
        * Identify algorithm’s basic operation which relates to input instance
        * Determine worst and best cases for input of size N
        * Count number of basic operations.
            * Rules:
                * Common constant operations:
                    * Addition, subtraction, multiplication, and division of fixed size integer or floating point values.
                    * Assignment of a reference, pointer, or other fixed size data value.
                    * Comparison of two fixed size data values.
                    * Read or write an array element at a particular index.
                * **Simplified runtime analysis:** A constant number of constant time operations is O(1).
                * **Method calls:** A method call has an analysis of m + 1, where m is the number of operations inside the method.
                * **Returns:** Return statements don’t count as an operation (that is part of the method call), unless the return statement does a calculation.
                * **Loops:** The number of operations inside a loop must be multiplied by the maximum number of times the loop could execute.
                * **Conditionals:** Each branch of a conditional will have it’s own cost. We need to multiply each branch by a likelihood factor.
                * **Exception handling:** Because exceptions happen rarely, and most often just result in an error being logged or printed out, we can usually just ignore this code.
            * Simplify the sum using standard formulas and rules
                * Ignore the lower-growth-order subexpression(s)
                * Ignore the coefficient of the highest-growth-order subexpression
* Example:   `4n3 + 2n2 + 6n + log n + 4  thus also simplifies to: O(n3) `

## Stacks and Queues
Stacks which are a Last In First Out (LIFO) model
Queues are what we call a First In First Out (FIFO)

Insert in end
Remove from the front

## Binary Search
Sorted list 1 2 3 4 5 16
Linear search O(n) All items have already been sorted.
Compare with search target
Smaller
Larger 
Or equal to

Chance to narrow down the search space
Don’t need to search the right half 
If 4 is smaller than the target 



Target : 7
2 4 6 11 16
Lower index:2 
High: 16
1st Iteration: calculate the mid index
Low: 0
High: 4

Mid: low + high / 2= 2
Test list[mid] == target
If it evaluates to be true
Return mid

If list[mid] < target
Target left half only focused. cannot be in the left side
Target larger in the middle then
Low = mid +1 ignore left half
Else 
High = mid -1


`if (list.isEmpty()) { 
	throw new EmptyCollectionException(); 
}
SingleLinkedNode curr = list.first(); 
SingleLinkedNode max = list.first(); 
	while (curr.getNext() != null) { 
		if (max.getElement().compareTo(curr.getElement()) < 0) { 
	max = curr; 
}
curr.setNext(curr); 
} 
return max.getElement(); 
}`

## Whiteboard Notes

Growth Scale/Rate

T(N) = 3N + 2 = O(N) <- Big O Notation
G(N) = 2N = O(N)

Let us denote N = k, T(N)/G(N) = (3n+2)/(2n) = (3k+2)/(2k) = 3/2

Now let us denote N = 2k, (T(N)/G(N)) = (3x)(2k)+2/(2x)(2k) = 3/2

T(N) = aN + b = O(N)

T(N) = 2N^2 + N + 3 -> O(N^2)
G(N) = N^2 = O(N^2)

1. Let us denote N = k (k is infinite)
T(N)/G(N) = (2N^2 + N + 3)/(N^2) = 2 + 1/N + 3/N^2 = 2 + 1/k + 3/k^2 = 2

2. Let us denote N = 2k, T(N)/G(N) = 2 + 1/2k + 3/((2k)^2) = 2

T(N) = aN^2 + bN + c = O(N^2)

Which of the following Big O notations is equivalent to O(N + 9999)?
	* 100000
	* 3
	* 2N + 1
	* N^2 + 1
        * N^2 - 10000
	* O(1)
	* **O(N)8**
	* O(N^2) 

`public static int search(int[] numbers, int targetNumber)
{
// int[] numbers <- Input size N
// For Loop performs N loops

  for (int index = 0; index < numbers.length; index++)
  {
    if (numbers[index] == targetNumber)
    {
      return index;
    }
  }
  return -1;
}`

T(N) = 3N + 2
O(N) = 3N + 2/3N + 1


