---
layout: post
title:  "What Are Algorithms"
date:   2020-11-28 12:36:11 -0700
categories: jekyll update
author: Juan Cobian
---

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
