# About

This document was used by [Kevin Owocki](http://owocki.com) in his Summer 2013 Job Hunt to prep for technical interviews.  Enjoy, and feel free to edit!   If you have any questions, my contact information is on [owocki.com](http://owocki.com/contact)

## Table of Contents

1. [General Knowledge](#general-knowledge)
2. [Data Structures](#data-structures)
5. [Bit Manipulation](#bit-manipulation)
6. [Brain Teasers](#brain-teasers)
7. [Object Oriented Design](#object-oriented-design)
8. [Recursion and Dynamic Programming](#recursion-and-dynamic-programming)
9. [Scalability and Memory Limits](#scalability-and-memory)
10. [Sorting and Searching](#sorting-and-searching)
10. [Design Patterns](#design-patterns)
11. [Testing](#testing)
12. [Threads and Locks](#threads-and-locks)
12. [Security](#security)
13. [Supplemental Resources](#supplemental-resources)
14. [Behavioral Interview Checklist](#behavioral-interview-checklist)

## General Knowledge

### Practice Questions

*Q*: Describe everything that happens from the time you hit enter, to the time your browser receives a response.

```
Roughly,

The browser resolves the URI* to an IP address.  (This will do a usual lookup - cache, hostfile then server.)
The browser sends a GET request to that IP.
The server finds the correct file.
The server processes the file.
The file is sent to you.
The server typically responds with a text stream and your browser displays it.
Browser fetches asset files (CSS/JS/Images).
*Uniform Resource Identifier
```

[See also, this attempt to answer this question as broadly as possible!](https://github.com/alex/what-happens-when)

*Q*: What is the w3c?

```
The World Wide Web Consortium (W3C) is the main international standards organization for the World Wide Web (abbreviated WWW or W3).

```

*Q*: Explain MVC in simple terms

```
MVC is a methodology in programming that is widely used for the ground works, we’re asking them to explain it in simple language because we also we also want a developer to be able to speak to non-technical people. We’ll give you 2 examples of simple explanations:
M (Model) stands for the part of the code that knows things.
V (View) is the part of the code that shows the things the Model knows.
C (Controller) is the part of the code that gets commands from the user and tells the View what to show and the Model what to know.
```

*Q*: Write a program that prints the numbers from 1 to 100. But for multiples of three print “Fizz” instead of the number and for the multiples of five print “Buzz.| For numbers which are multiples of both three and five print “FizzBuzz.”


```
 Public Sub fizzbuzz()
  For n = 1 To 100
	Select Case 0
		Case n Mod 15
		f = "FizzBuzz"
		Case n Mod 3
		f = "Fizz"
		Case n Mod 5
		f = "Buzz"
		Case Else
		f = n
	End Select
	Debug.Print f
	Next n
 End Sub


```

*Q*: What is REST?

```
REST (REpresentational State Transfer) is a simple stateless architecture that generally runs over HTTP.   REST is an "architectural style" that basically exploits the existing technology and protocols of the Web.  There are generally 4 actions on a RESTful service:
* Create
* Read
* Update
* Delete
```

*Q*: Explain ways to improve a page load speed or user experience.

See [Front End Performance Checklist](http://developer.yahoo.com/performance/rules.html)
On the backend,
* Caching
* Solid Architecture
* Horizontal Scalability

*Q*: Explain a number of HTTP status codes (except maybe 404 and 500).

See [List of HTTP Status Codes](http://en.wikipedia.org/wiki/List_of_HTTP_status_codes)

*Q*: What is a closure in JavaScript?

A method and properties that outlive the scope of their original function

*Q*: What is the maximum value of a 32bit integer?

Signed? 2^32= 4.2 billion
Unsigned? 2^(32-1)= 2.1 billion

*Q*: How many bytes are in a 32bit integer?

32/8 = 4 bytes

*Q*: Number of times 7 appears in the list of number 1 - 100?

In the range 1 - 100, the digit 7 appears ten times in the second decimals place, and ten times in the first decimals place, for a total of twenty appearances.

*Q*: Discuss pros/cons of OOP, Procedural, Functional, Event-Driven, programming.

* Imperative programming – defines computation as statements that change a program state
* Procedural programming, structured programming – specifies the steps the program must take to reach the desired state.
* Declarative programming – defines computation logic without defining its control flow.
* Functional programming – treats computation as the evaluation of mathematical functions and avoids state and mutable data
* Object-oriented programming (OOP) – organizes programs as objects: data structures consisting of datafields and methods together with their interactions.
* Event-driven programming – the flow of the program is determined by events, such as sensor outputs or user actions (mouse clicks, key presses) or messages from other programs or threads.
* Automata-based programming – a program, or part, is treated as a model of a finite state machine or any other formal automata

[More on wikipedia](http://en.wikipedia.org/wiki/Comparison_of_programming_paradigms)



### Sample problems:

#!TODO

## Data structures

### Arrays and Strings

An array is data structure (type of memory layout) that stores a collection of individual values that are of the same data type.  All of the items placed into an array are automatically stored in adjacent memory location.

An ArrayList is a dynamically resizing array.  It doubles in size each time the array is full.  Doubling is O(n), but lookups are O(1).

A StrinbBuffer is an array of strings.  Storing the strings as an array allows you to avoid the O(xn^2) problem of concatenating *n* strings.

### Practice Questions

*Q*: Implement an algorithm to determine if a string has all unique characters.  

*Q*: Implement a function void reverse(char * str) in C, C++ which reverses a null terminated string.

*Q*: Given two strings, write a method to decide if one is a permutation of the other

*Q*: Implement a method to perform basic string compression using the counts of repeated characters.  For example, the string aacccccaaa would become a2b1c5a3.  If the compressed string is not shorter than the original string, then return the original string.

*Q*: Given an image represented by an NxN matrix, where each pixel in the image is 4 bytes, write a method to rotate the image by 90 degrees.  Bonus points: do this in place.

*Q*: Assuming you have a method *isSubstring()* which checks if one string is a substring of another, write code to check if s2 is a rotation of s1 using only one call to *isSubstring()*.  ex: pineapple is a rotation of apppinele.

## !TODO

### Linked Lists

A __singly linked list__ contains nodes which have a data field as well as a next field, which points to the next node in the linked list.   It is often used as a stack (or last in first out queue (LIFO)) because adding a new first element, removing the existing first element, and examining the first element are very fast O(1) operations.

A __doubly linked list__ is a linked data structure that consists of a set of sequentially linked records called nodes. Each node contains two fields, called links, that are references to the previous and to the next node in the sequence of nodes

[More via wikipedia](http://en.wikipedia.org/wiki/Doubly_linked_list)

### Practice Questions

*Q*: How can you find a 'cycle' in a singly linked list?

1. Use Memory Allocation Information.  - Keep track of the minimum or maximum memory addresses seen.  If more nodes have been seen than can fit in the address space then some node must have been a cycle.
2. Two iterators - Go through the list one by one (with a slow iterator) and by twos (fast iterator).  If the fast iterator laps the slow iterator, the linked list has a 'cycle.

*Q*: Write an algo to remove duplicates from an unsorted linked list.

*Q*: Implement an algorithm to find the n-th element of a singly linked list.

*Q*: Implement an algorithm to delete a node in the middle of a singly linked list, given only access to that node.

*Q*: Implement an algorithm to partition a linked list around value z.  All nodes less than z come before all nodes greater than or equal to z.

*Q*: Given a circular linked list, implement an algorithm which returns the node at the beginning of the loop.

*Q*: Implement an algorithm to check if a linked list is a palindrome.

*Q*: Implement a 'Hash table'.


### Stacks and Queues

A stack is a data structure which contains a list of elements with LIFO (last in first out) ordering.  The most recent item added (push()ed) to the stack is the first item to be removed (pop()ed).  

A queue is a FIFO (first in, first out) data structure.  The most recent item added (enqueu()ed) is the last item to be removed from the queue (dequeu()ed).


### Practice Questions

*Q*: Implement a stack.  Implement a queue.

*Q*: How would you use a single array to implement three stacks?

*Q*: Design a stack that has a method `min()` which returns the minimum element in O(1) time.

*Q*: Implement a data structure `SetOfStacks` which contains several stacks and will create a new stack when a stack in the set exceeds a certain capacity (positive integer).  Implement `SetOfStacks.push()` and `SetOfStacks.pop()`.

*Q*: Write an algorithm that solves the [Towers of Hanoi](http://en.wikipedia.org/wiki/Tower_of_Hanoi) problem using stacks.

*Q*: Implement a Queue class which implements a queue using two stacks.

*Q*: An animal shelter holds only dogs and cats, and operates on a strictly “first in, first out” basis. People must adopt either the “oldest” (based on arrival time) of all animals at the shelter, or they can select whether they would prefer a dog or a cat (and will receive the oldest animal of that type). Create the data structures to maintain this system and implement operations such as enqueue, dequeueAny, dequeueDog and dequeueCat. You may use the built-in LinkedList data structure (has “addLast” method to insert an element at the end of the list, “poll” method to pop the first element of the list and “peek” method to get the first element).

*Q*:  Write an array-based implementation of a queue that uses a circular array to represent the items in the queue. It should have two array indexes - front and rear - where front should point to the front of the queue and rear should point to the back of the queue. Use variable MAX_QUEUE to indicate the maximum number of elements that could be stored in the queue. Obtain the wrap around effect by using modulo arithmetic (the JAVA % operator).

!TODO answers

### Trees and Graphs

A *Binary tree* is a tree data structure in which each node has at most two child nodes, usually distinguished as "left" and "right". Nodes with children are parent nodes, and child nodes may contain references to their parents. Outside the tree, there is often a reference to the "root" node (the ancestor of all nodes), if it exists. Any node in the data structure can be reached by starting at root node and repeatedly following references to either the left or right child. A tree which does not have any node other than root node is called a null tree. In a binary tree, a degree of every node is maximum two. A tree with n nodes has exactly n−1 branches or degree.

*Binary search tree (BST)*, sometimes also called an ordered or sorted binary tree, is a node-based binary tree data structure which has the following properties:[1]
** The left subtree of a node contains only nodes with keys less than the node's key.
** The right subtree of a node contains only nodes with keys greater than the node's key.
** The left and right subtree must each also be a binary search tree.
** There must be no duplicate nodes.

A tree is 'unbalanced' if the depth of the subtrees varies by more than a certain amount.

A tree is 'full' or 'complete' if all leaves are at the bottom of the tree and all non-leaf nodes have exactly two children.

### Practice Questions

### !TODO

### Hashmap

A hash map is a data structure used to implement an associative array.   A hash table uses a hash function to compute an index into an array of slots, from which the correct value can be found.

The hash function (ideally) assigns each possible key to a unique bucket, but there are, in practice, hash collisions.

There are several strategies to collision resolution.
* Seperate chaining - Each bucket has a list of entries.
* Open addressing - All entry records are stored in teh bucket itself.
* Hopscotch hashing - define a 'neighborhood' of buckets near the original hased bucket, and then search limited to that neighborhood.  If all buckets in that neighborhood are taken, iterate across array.

### Practice Questions

### !TODO




##  Bit manipulation

### Bit operations

```
&   -  bitwise and
|   -  bitwise or
^   -  bitwise xor
~   -  bitwise not
<<  -  bitwise shift left
>>  -  bitwise shift right
```

### Some bit hacks

```
Bit Hack #1. Check if the integer is even or odd.

if ((x & 1) == 0) {
  x is even
}
else {
  x is odd
}


Bit Hack #2. Test if the n-th bit is set.

if (x & (1<<n)) {
  n-th bit is set
}
else {
  n-th bit is not set
}

Bit Hack #3. Set the n-th bit.

y = x | (1<<n)

Bit Hack #4. Unset the n-th bit.

y = x & ~(1<<n)

Bit Hack #5. Toggle the n-th bit.

y = x ^ (1<<n)

Bit Hack #6. Turn off the rightmost 1-bit.

y = x & (x-1)

Bit Hack #7. Isolate the rightmost 1-bit.

y = x & (-x)

```

[More bit hacks](http://www.catonmat.net/blog/low-level-bit-hacks-you-absolutely-must-know/)

### Practice Questions

### !TODO


## Brain Teasers

#### Strategy and Approach to Answering a Problem Solving Interview Question

If you get asked a problem solving question in an interview, remember that they are NOT looking for the RIGHT answer.  They are evaluating  the approach you use to think out and solve the problem.  A strong candidate demonstrates the following:

1. Evaluates and understands the scope of the problem
1. Communicates assumptions
1. Demonstrates quantitative analytical skills
1. Answers the question that has been asked. You’d be surprised how many candidates get lost in the analysis and solve for a different question than what was asked.

#### Five simple approaches to brain teaser problems:

1. __Examplify__ - Write out specific examples of the problem and see if you can derive a general rule.
2. __Pattern Matching__ - Consider problems that the algorithm is similar to and try to modify the solution to the related problem.
3. __Simply and Generalize__ - Change a constraint in a way that allows you to simplify problem.  Once you have an algorithm for a simplified problem, generalize the problem to the complex version.
4. __Base Case and Build__ - Solve the problem first for a base case (ex: n = 1)  Then solve for n =2, 3, and onwards. 
5. __Data Structure Brainstorm__ - Run through a list of data structures and apply each one.


[Some Warm up Questions](http://questionsininterview.com/welcome-to-questionsininterview-com/problem-solving-interview-questions/)

## Object Oriented Design

### !TODO

## Recursion and Dynamic Programming

### !TODO

## Scalability and Memory Limtis

### !TODO

## Sorting and Searching

* __Bubble sort __ -
* __Selection sort __ -
* __Insertion sort __ -
* __Shell sort __ -
* __Comb sort __ -
* __Merge sort __ -
* __Heapsort __ -
* __Quicksort __ -
* __Counting sort __ -
* __Bucket sort __ -
* __Radix sort __ -
* __Distribution sort __ -

TODO Definitions [here](https://en.wikipedia.org/wiki/Sorting_algorithm)

## Design Patterns 

 * __Abstract Factory__ groups object factories that have a common theme.
 * __Builder__ constructs complex objects by separating construction and representation.
 * __Factory__ Method creates objects without specifying the exact class to create.
 * __Prototype__ creates objects by cloning an existing object.
 * __Singleton__ restricts object creation for a class to only one instance.
 * __Adapter__ allows classes with incompatible interfaces to work together by wrapping its own interface around that of an already existing class.
 * __Bridge__ decouples an abstraction from its implementation so that the two can vary independently.
 * __Composite__ composes zero-or-more similar objects so that they can be manipulated as one object.
 * __Decorator__ dynamically adds/overrides behaviour in an existing method of an object.
 * __Facade__ provides a simplified interface to a large body of code.
 * __Flyweight__ reduces the cost of creating and manipulating a large number of similar objects.
 * __Proxy__ provides a placeholder for another object to control access, reduce cost, and reduce complexity.
 * __Chain of responsibility__ delegates commands to a chain of processing objects.
 * __Command__ creates objects which encapsulate actions and parameters.
 * __Interpreter__ implements a specialized language.
 * __Iterator__ accesses the elements of an object sequentially without exposing its underlying representation.
 * __Mediator__ allows loose coupling between classes by being the only class that has detailed knowledge of their methods.
 * __Memento__ provides the ability to restore an object to its previous state (undo).
 * __Observer__ is a publish/subscribe pattern which allows a number of observer objects to see an event.
 * __State__ allows an object to alter its behavior when its internal state changes.
 * __Strategy__ allows one of a family of algorithms to be selected on-the-fly at runtime.
 * __Template method__ defines the skeleton of an algorithm as an abstract class, allowing its subclasses to provide concrete behavior.
 * __Visitor__ separates an algorithm from an object structure by moving the hierarchy of methods into one object.

### TODO Questions


## Testing

### !TODO

## Threads and Locks

### !TODO

## Security

XSS

SQL Injection

CSRF

Man in the middle

### !TODO

## Supplemental Resources

* [Big-O Cheat Sheet](http://bigocheatsheet.com/)
* [Reg Ex Cheat Sheet](http://regexlib.com/CheatSheet.aspx)
* [Powers of 2 table](http://www.vaughns-1-pagers.com/computer/powers-of-2.htm)
* [Cracking the coding interview](http://www.amazon.com/books/dp/098478280X)


### List of relevant programming languages / frameworks


#### Server Scripting
| Name        | Description           | Comments  |
| ------------- |-------------------------------| -----------------------|
| Clojure      | TODO |  |
| Django      | TODO |  |
| Go      | TODO |  |
| Lisp      | TODO |  |
| Node      | TODO |  |
| PHP      | TODO |  |
| Python      | TODO |  |
| R      | TODO |  |
| Ruby / Rails      | TODO |  |
| Java      | TODO |  |
| Scala      | TODO |  |

#### Client Side 

| Name        | Description           | Comments  |
| ------------- |-------------------------------| -----------------------|
| Angular      | TODO |  |
| Backbone      | TODO |  |
| Javascript/jQuery      | TODO |  |
| HTML5      | TODO |  |
| CSS3      | TODO |  |

#### Data storage 

| Name        | Description           | Comments  |
| ------------- |-------------------------------| -----------------------|
| BerkeleyDB      | TODO |  |
| Cassandra      | TODO |  |
| CouchDB      | TODO |  |
| Redis      | TODO |  |
| Hadoop      | TODO |  |
| ElasticSearch      | TODO |  |
| Memcache      | TODO |  |
| MemcacheDB      | TODO |  |
| MongoDB      | TODO |  |
| MariaDB      | TODO |  |
| PostegresSQL      | TODO |  |
| MySQL      | TODO |  |
| SQLLite      | TODO |  |
| Graph Databases      | TODO |  |

#### APIs / Other 

| Name        | Description           | Comments  |
| ------------- |-------------------------------| -----------------------|
| Analytics (MixPanel, KISSMetrics)      | TODO |  |
| Facebook      | TODO |  |
| LinkedIn      | TODO |  |
| Twitter      | TODO |  |
| Android      | TODO |  |
| iOS      | TODO |  |
| Mailing Clients (Sendgrid, Sailthru,MailChimp)      | TODO |  |
| Messaging Queues      | TODO |  |
| Firebase      | TODO |  |
| Graphite      | TODO |  |

## Web Hosts
| Name        | Description           | Comments  |
| ------------- |-------------------------------| -----------------------|
| Amazon      | TODO |  |
| Rackspace      | TODO |  |
| Google      | TODO |  |
| Azure      | TODO |  |
| Managed Hosts (EngingeYard, etc)      | TODO |  |



### Payment Gateways

| Name        | Description           | Comments  |
| ------------- |-------------------------------| -----------------------|
| Braintree      | TODO |  |
| Authorize.net      | TODO |  |
| Stripe      | TODO |  |
| Paypal      | TODO |  |


## Behavioral Interview Checklist

### Behavioural Questions.

1. Why do you want to work for *X*?
2. Why should we hire you at *X*?
3. What is your greatest weakness?
4. What is your biggest strength?
4. Do you have any questions for me?
5. Where do you see yourself in 5 years?
6. Why are you leaving your current company?
7. What blogs do you read?  How do you keep up with tech news?


## Past Projects

Often on these questions, interviewers are looking for three things (be succinct):
* Situation: outline the situation
* Action: what action did you take?
* Response: What was the result?

3. What was the most technically challenging part of (last project)?
4. What'd you learn the most from (last project)?
5. What was the most interesting part of (last project)?
6. What was the hardest bug?
7. What'd you enjoy the most?
8. Give me an example of a conflict with a past teammate.
9. Give me an example of a decision you made that was unpopular.

### Do your research on the company.

1. Look @ Glassdoor Reviews.
1. Look @ Recent press & fundraise announcements.
1. Who are the founders? What are their backgrounds?
2. Research interviewer

<!-- Google Analytics --> 
<img src='https://ga-beacon.appspot.com/UA-1014419-15/owocki/interview_prep_checklist' style='width:1px; height:1px;' >

