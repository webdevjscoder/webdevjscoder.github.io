## Computer Science Notes

# Why Algorithms?

What is an algorithm?

* is a sequence of actions set to be performed
* in other works a procedure to perform tasks
* very vague and to the point

Why learn algorithm?

* most if not all languages lean on them to solve problems
* someone prior to us has probably already solved an issue we run into
and therefore must have an algorithm we can if appropriate, apply it to our code
* one of the dangers with algorithms is the misconception of how to prioritize our code
because they often times ask us to consider how long a procedure takes
* priorities should still be as followed
 * make it work
 * make it right (i.e., readable)
 * make it fast

# Time Complexity

* Our first algorithm
 * is the letter 'a' in a given word 'banana'
 
* this can be solved with Javascript's includes method

`'banana'.includes('a') // true`

* how does javascript implement something like this?
* lets say they would implement it like we would, by checking every letter

** Cost of examining each letter **

* 'cost' in the terms of algorithms, it means the 'time'
* we are calculating the time it takes to evaluate each letter and test for equality

`function stringIncludes(word, letter){
     let matches;
     for(let i = 0; i < word.length; i++){
       if(word[i] === letter){
         matches = true
       }
     }
     return !!matches
   }
  
   stringIncludes("banana", "a")
   // true
   stringIncludes("banana", "d")
   // false`
   
* function is defined now calculate the time

`function stringIncludes(word, letter){
   let matches; // 1
   for(let i = 0; i < word.length; i++){ //2
     if(word[i] === letter){ //3
       matches = true //4
     }
   }
   return !!matches // 5
 }
  
 stringIncludes("banana", "d")`
 
 * when asked how long did a procedure take, a shorthand is to count the lines of code invoked
 * in this case it was 5 lines
 * take a closer look if we were look for the letter 'd'
 
 `function stringIncludes(word, letter){
    let matches; // 1
    for(let i = 0; i < word.length; i++){ //2
      if(word[i] === letter){ // + 6
        matches = true //
      }
    }
    return !!matches // 9
  }
   
  stringIncludes("banana", "d")`
  
* first line we declare a variable let matches;
* then we iterate over every letter in the word 'banana' which is 6
* so we run the if expression 6 times
* finally coerce the variable matches to return its boolean value
* all in all it would be somewhere around 9 steps involved

* notice the time it take to guarantee the letter in not in the string

* if let the number of letters in our word be n then we can say our function
 runs in n + 3 time 
 * so if we choose a string of 100 letters, this takes 100 + 3 = 103 time 
 * we call this the time complexity of the function
 
 ** A lingering problem **
 
 * Doesn't time complexity depend on the match
 * if we were looking for the letter 'b' in banana would take less time to run?
 * we will leave this for the next section and appreciate what we've learned so far.
 
 ** Summary **
 
 * we worked towards determining how costly a function really is
 * we calculated the 'cost' by counting the lines that are run in a function
 * we recognized the cost of performance is determined by the size of the input
 * we call the cost the 'time complexity' of the function
 
 ------------------------------------------------------------------------------
 
 # Worst Case Complexity
 
 * we determined in the last section the time complexity of a function in terms of the length
 of the input
 * we also noted that it depends on if there is a matching letter or not and the position of the
 matching letter
 
 `function stringIncludes(word, letter){
      let matches;
      for(let i = 0; i < word.length; i++){
        if(word[i] === letter){
          return matches = true
        }
      }
      return !!matches
    }
   
    stringIncludes("banana", "b")
    // true
    stringIncludes("banana", "d")
    // false`
    
* checking for the letter 'b' in 'banana' has a cost of 3
* checking for 'd' in 'banana' has a cost of 9 (n + 3)
* this is called the best and worst case scenarios
* where the shortest amount of time is the best case
* and where the most amout of time is the worst case

** Best, Average, worst? Always chose worst. **

1. ** Best Case **

* the best case scenario for our function is to ask the question whether 'b' is in the word 'banana'
* that is the fewest amount fof step of function can take 3

* disregard the best case scenario and not even care about it
* why? well, calculating the best case scenario for a computer is the same, fast enough that the
performance is not an issue
* this about it like this

`let fruit = "banana"
   let letter = "b"
   function stringIncludes(fruit, letter){
     alert('ask a six year old child if "banana" includes the letter b')
   }`
   
* both our function will still be pretty performant
* doesn't make sense to optimize over two functions' case scenarios because both will take the same
amount of time: very little

2. ** Average Case **

* when calculating the performance of an algorithm, we typically don't think about the average case
* this is because it is very difficult to determine the average

* to calculate the average cost in our function we would have to take all the words in the english language
* also all the letters in the alphabet
* and see how the function performs
* we would also have to consider the popularity of those words and how often they would be passed as arguments
* we might get the average cost wrong and if we optimize for the wrong case, then our algorithm will take a long time
* so in order words, when coding its best not to use the average case

3. ** Worst Case **

* we didn't choose best case because all algorithms look good when consider the best case
* we didn't choose the average case because it difficult to calculate the average case
* the worst can be calculated without looking at streams of data
* when evaluating how it takes consider the worst case scenario
* worst case scenario: someone gives you an input of a specific size and wants your procedure to take as
long as possible

* the worst our function could ever perform for the string 'banana' is 9
* it must go through every letter, and three other operations

** Summary **

* we have determined the time complexity means the number of lines of code we run in the worst case
* where the worst case is when we receive a certain input and our function takes as long as possible
* we can determine the worst case scenario be the size of the input
* for our function the worst case scenario would be when we have to go through every letter of the string and add 3
* calling the length of our input 'n', we would say the cost of our function is n + 3

----------------------------------------------------------------------------------------------------------------

# Big O Approximation

* in the last section we consider the worst case because we tend to feel the costs of performance
* since computers are so fast we will consider datasets much bigger
* by this I mean in the tens of thousands

* time complexity sometimes is called asymptotic time complexity
* asymptotic means:
 * as n (ie. the length of our input) approaches infinity
 
* the worst case scenario is determined by asking what's the worst case when the input gets really large

** Second Algorithm **

* previously we determined if a random string included a letter by considering each letter

`let string = "banana"
 let letter = "a"
  
   function stringIncludes(string, letter){
     let matches;
     for(let i = 0; i < string.length; i++){
       if(string[i] === letter){
         matches = true
       }
     }
     return !!matches
   }
  
   stringIncludes(string, letter)`
   
* this time we will sort our letters in alphabetical order
* we will discuss cost of time in a different section

`function sortString(string){
     return string.split('').sort().join('')
   }
   sortString("banana")
   // "aaabnn"
  
   sortString("itwasthebestoftimesitwastheworseoftimes")
   // "aabeeeeeeffhhiiiimmooorsssssstttttttwww"`
   
** Introduction of Binary Search **

* given two questions
* whether given the chose to find the letter 'u' in the string "itwasthebestoftimesitwastheworseoftimes"
* or in the same string but sorted "aabeeeeeeffhhiiiimmooorsssssstttttttwww", which would be faster for you?

* the second one right? in answering you would no longer look at each letter one by one
* instead would look at the middle and see if its 'i'
* move further down past the 't' section and the 'w' know it is not there
* this is called the phone book method

* if looking for a name in the phone book
* we wouldn't be looking one page at a time
* we know the name we are looking for and the starting letter
* we would flip the book at the half point and determine whether we are too far up or down
* we would then proceed to flip it in half  again whether its up or down until we found the name

* binary search tree divides the dataset with each attempt to find a match

* new technique and old technique side by side

`// one by one
   function stringIncludes(string, letter){
     let matches;
     for(let i = 0; i < string.length; i++){
       if(string[i] === letter){
         matches = true
       }
     }
     return !!matches
   }
  
   function binarySearch(string, letter) {
     var startpoint = 0
     var endpoint = string.length - 1;
     var guessPosition = parseInt((endpoint - startpoint)/2)
     while (startpoint != endpoint) {
       console.log(`start point is ${startpoint}, endpoint is ${endpoint} and guessposition is ${guessPosition}`)
         if (string[guessPosition] < letter) {
           console.log('too low')
             startpoint = guessPosition
             guessPosition = startpoint + Math.round((endpoint - startpoint)/2)
         } else if(string[guessPosition] > letter) {
           console.log('too high')
             endpoint = guessPosition
             guessPosition = startpoint + parseInt((endpoint - startpoint)/2)
         } else {
           console.log('just right')
             return true;
         }
     }
     if(string === letter){
       return true
     } else{
       console.log('sorry')
       return false;
     }
   }
  
   let string = "aabeeeeeeffhhiiiimmooorsssssstttttttwww"`
   
* these two functions are vastly different
* lets determine the time complexity

1. Consider the worst case scenario in both functions

* the worst case would be the same for each function
* they would keep keep guessing until coming to the conclusion that the letter is not in the string

2. Calculate the cost as the size of out input grows

* for our first function we already determined it was n + 3, where n is the size the string
* what about the new binarySearch function?
* there is a lot involved to calculate an actual number
* lets focus on the biggest determinant: how many times we travel through the while loop
* the function cuts what we search through in half every time we pass through the loop

|----------------|-------------------|
| Input size (n) | Number of guesses |
|----------------|-------------------|
|   1            |   0               |
|----------------|-------------------|
|   2            |   1               |
|----------------|-------------------|
|   4            |   2               |
|----------------|-------------------|
|   8            |   3               |
|----------------|-------------------|
|   16           |   4               |
|----------------|-------------------|
|   1024         |   10              |
|----------------|-------------------|
|   2048         |   11              |
|----------------|-------------------|
|   4096         |   12              |
|----------------|-------------------|
|   1,048,576    |   20              |
|----------------|-------------------|
|   n            |   log2(n)         |
|----------------|-------------------|

* as the size of the input increases, the number of guesses increase also increase, but slowly
* you can answer the question whether a letter is included in a sorted string over a million 
characters long in only 20 guesses

* just like we were about to determine the time complexity of out first function
* we can do the same for our binary search
* the time complexity is log2(n) (log base 2 of n, as written as lg(n))
* log2(n) means the number of times one would have to press 'divided by two' on the calculator to get to 1
starting with the number n

* with a size of n over a million our binary search algorithm would still take about 20 guesses
* with our first algorithm it would take us over a million guesses
* log2(n) algorithm input doubles but runtime goes up by 1

** Simplifying Time Complexity **

* meaningless to add 3 to our cost for the first three line in our binary search function
* the cost of binary search would still only be eight for an input of over a million

* considering time complexity we never care about add or multiplying
* we care about the leading exponent of our formula
* coefficients means anything that we multiply by n 
* exclude lower order terms means that we should only consider 'term' with the highest exponent
* For example, let's say that the time complexity of our function is 5n^3 + n^2 + 100n + log2(n) + 100
* Here n^3, n^2, 100n, log2(n) and 100 are all "terms" of the function 
* Excluding the lower order terms we would say that the time complexity of our function is 5n^3, and
 excluding n^3's coefficient of 5 we would say that the time complexity is n^3
 
 * considering the time complexity of our function is n^3 + n^2 + n + log2(n) + 100 and assume that n is 1,000
 
 |-------------|-------------|-----------|------------|----------------|--------------------------------|
 |   Formula   |   log2(n)   |      n    |     n^2    |     n^3        |  n^3 + n^2 + n + log2(n) + 100 |
 |-------------|-------------|-----------|------------|----------------|--------------------------------|
 |    n=1000   |     9.9     |    1000   |  1,000,000 |  1,000,000,000 |         1,001,001,110          |
 |-------------|-------------|_----------|------------|----------------|--------------------------------|
 
* formula above return approximately 1,001,001,110 if n is 1000
* the leading exponent in this case n^3 is dominant it terms of overall cost (n^2 doesn't move the dial)
* this is with a relatively small number. imagine when its in the ten thousands
* if possible to exclude n^2 we can also exclude anything number that we multiply n by
* this is because it will not make a big enough impact to count it
* we care about things that will cause n to approach infinity

* considering asymptoptic time complexity we only look at the largest exponent
* we only consider the worst case scenario
* we ignore coefficients as well as any smaller terms
* this is called big O

* now that we know how to express the cost of an algorithm by only considering the term with largest exponent
* is there a good technique to calculate the largest exponent? Yes

`function nSquared(string, letter){
   let matches;
   for(let i = 0; i < string.length; i++){ // loop 1
     for(let i = 0; i < string.length; i++){ // loop 2
       ...
     }
   }
  
 }
  
 nSquared("abc")`
 
* the big O of the function above is n squared
* reason is because loop 2 has a cost of three (passing 'abc')
* loop 1 runs the inner loop three times
* with the cost of three, three times leads the total cost of nine
* define the string length as n, we get n^2

`function nCubed(string, letter){
   let matches;
   for(let i = 0; i < string.length; i++){ // loop 1
     for(let i = 0; i < string.length; i++){ // loop 2
         for(let i = 0; i < string.length; i++){ // loop 3
           ...
         }
     }
   }
 }`
 
 * one way to determine the cost of the above function is by examining the content inside of loop 1 is the
 same big O as the nSquared function
 * so we come up with calculation of nSquared function n times, n*n^2 or n^3
 
 * Here's the point: to calculate the big O of a function if each loop forces you to go through your dataset n 
 times, just count the number of nested loops
 
 * the big O of the function below is not n^2, its just n
 * do you see why?
 
 `function notNSquared(string, letter){
    let matches;
    for(let i = 0; i < string.length; i++){
      if(string[i] === letter){
        matches = true
      }
    }
    for(let i = 0; i < string.length; i++){
      if(string[i] === letter){
        matches = true
      }
    }
  }`
  
* we don't go through the loop n times
* we only go though a loop two times
* cost is 2n but we ignore multipliers we have a big O of n
* So we don't just count the loops and automatically increase the big O by a factor of n
* we consider nested loops and ONLY loops whose iterations are proportional to n (e.g. which 
iterate through our dataset)

* counting visible loops in our code is helpful but not fail-safe to determine runtime
* we have to account for built-in functions
* example word be if we had a single loop and within that loop we use a sort method
* sorting algorithm would be O(n * log2(n))
* runtime is now O(n * n * log2(n)), which is O(n^2 * log2(n)) with a single loop

** Summary **

* we learned that as the size of the input grows (into the tenth of thousands), the leading exponent dominates
our calculation of the cost of the algorithm
* we ignore the smaller exponents, multipliers of an exponent and any number we need to add by
* we also learned how to calculate the big O of a function by counting the nested loops

--------------------------------------------------------------------------------------------------------------

# Recursion

** Terminology **

* recursive function is a function that calls themselves

`function sayDownFrom(n){
   console.log(n)
   if(n > 1){
     sayDownFrom(n -1) // recursive call
   } else {
     return true // base case
   }
 }
  
 sayDownFrom(5)
 // 5
 // 4
 // 3
 // 2
 // 1`
 
 * within the function you can see the function call itself (sayDownFrom(n -1))
 * the function has a stopping point which is called the base case
 * if no base case is provided the function would keep running and blow by 1 into the negative numbers
 
 * recursive is taught for two reasons
  1. we constantly think of recursive answers, so being able to put into code is an important tool
  2. some popular algorithms have recursive solutions, so understanding these common solutions help solve the problems
  
** An Initial Problem **

* consider this problem

`function sumUpToFive(){
   return (1 + 2 + 3 + 4 + 5)
 }`
 
 * which equals
 
 `function sumUpToFive(){
    return (1 + 2 + 3 + 4) + 5
  }`
  
 * consider the set of parenthesis around 1 and four
 * isn't it the same thing as sum up to four?
 
 `function sumUpToFive(){
    return sumUpToFour + 5
  }
   
  function sumUpToFour(){
    return (1 + 2 + 3) + 4
    // note (1 + 2 + 3) is the same as sumUpToThree
  }`
  
* if we wrote a function sumUpTo(n), it would equal something like 
* sum up n -1
* and n

`function sumUpToFive(){
   return sumUpToFour + 5
 }
  
 function sumUpToFour(){
   return sumUpToThree + 4
  
 }
  
 function sumUpToThree(){
   return sumUpToTwo + 3
 }
  
 function sumUpToTwo(){
   return (sumUpToOne + 2) 
 }
  
 function sumUpToOne(){
     return 1
 }`
 
* if so we can create a function like so

`function sumUpTo(n){
     sumUpTo(n - 1) + n
   }`
   
* however this function will continue to run forever because we have no base case

`function sumUpTo(n){
   if(n > 1){
       sumUpTo(n - 1) + n
   } else {
     return 1
   }
 }`
 
** How the computer executes a recursion **

`function sumUpTo(n){
   if(n > 1){
       sumUpTo(n - 1) + n
   } else {
     return 1
   }
 }
  
 sumUpTo(5)
   // this translates to
   sumUpTo(4) + 5
     // then JavaScript translates sumUpTo(4) as
     sumUpTo(3) + 4
       sumUpTo(2) + 3
         sumUpTo(1) + 2
           // 1`
           
* this is basically say 'hey run until sumUpTo(1) and return'
* there are two steps involved here
* first javascript repeatedly calls the sumUpTo function until it reaches the base case
* once that it done it will begin to solve the other function calls

** Discovering a recursive solution **

* knowing now that there is two steps involved to our sumUpTp
* first breaking down the recursive calls until the base case is reached
* then when the base case is resolved, then the other recursive calls are solved

* now lets see how we get a recursive solution
* we don't this by using the breakdown and build back up process
* we do so by rewording as so

1. given the problem sumUptTo(n) we can solve with

`sumUpTo(5)
     // 1 + 2 + 3+ 4 + 5`
     
2. can we reword the solution with the name of our function

* we know that 1 + 2 + 3 + 4 + 5 is really sumUpTo(4) + 5
* what would it mean to print out all the nu,bers down from 5
* it would be the opposite and we will print out 5 then print out downFrom(4), etc
* leading to a recursive call of downFrom(n - 1)
* last thing to do it set a base case

** Summary **

* we learned to find a recursive solution to a problem
* how javascript evaluates a recursive solution
* we also learned that javascript will make multiple calls until the base case is reached
* once provided with a solution, then the other recursive solutions can be solved, one by one
until we have arrived at our solution

-----------------------------------------------------------------------------------------------