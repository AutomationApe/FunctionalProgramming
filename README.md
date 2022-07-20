# FunctionalProgramming

What is Functional Programming?
    
    Functional programming is another paradigm, or programming model, based on writing code that focuses on separating concerns. In this paradigm, the 
    concerns are separating data and functions. The data gets interacted and acted upon, while the functions operate on well defined data structures 
    such as lists and dictionaries. 
    
    The idea for both paradigms is to design code that adheres to the following:
      
      Clear + Understandable
      Easy to Extend
      Easy to Maintain
      Memory Efficient
      DRY
    
    Functional Programming only has one "pillar" and that is Pure Functions. Which is the idea that there is a separation between the data of a program
    and the behavior of the program.
    
Pure Functions

    Pure functions follows two rules, the first being that each time its run with the same input, it will always return the same output.
    The second rule is the idea that a function should not produce any side effects, affecting the outside world. 
    
    ex:
    
      def multiply_by2(li):
        new_list = []
        for item in li:
          new_list.append(item*2)
        return new_list
        
      print(multiply_by2([1,2,3]))
     
    This is an example of functional code as it follows the rule previously stated rules. It will always produce the same results and does not affect
    the outside world.
    
    Pure functions create clean, safe code. * It is not possible to always create functional code, but when possible, you should *
    
map()

    The map() function allows us to simplify our code. For example, the multiply_by2 function from above, when combined with the power of the map()
    function, would look like this:
    
        my_list = [1,2,3]
        def multiply_by2(item):
            return item*2
            
        print(list(map(multiply_by2, my_list))) -> outputs [2,4,6]
        print(my_list) -> outputs [1,2,3]
        
    This would output the same results as before, but with less code. The reason this works is because the map() function takes two parameters, an 
    action to be performed, and an item to iterate over. In this case, our action to be performed is our multiple_by2 function and our item to iterate
    over is our list. map() also creates a new list to store the results, so we don't even need to create a new list explicitly and our original list
    does not get changed, therefore following the two rules of pure functions.
    
For more information on map():
https://www.programiz.com/python-programming/methods/built-in/map

filter()

    The filter() method filters out some results. For example, you could use filter() if you are wishing to only receive results that are odd numbers:
    
        my_list = [1,2,3]
        def multiply_by2(item):
           return item*2
        
        def only_odd(item):
            return item % 2 == 0
            
        print(list(filter(only_odd, my_list))) -> outputs [1,3]
        print(my_list) -> outputs [1,2,3]
 
For more information on filter():
https://www.programiz.com/python-programming/methods/built-in/filter

zip()

    The zip() function works simlarly to a zipper. We are able to grab items from two different collections and join them together. For example, take 
    the following code:
    
    my_list = [1,2,3]
    your_list = [10,20,30]
    
    print(list(zip(my_list, your_list))) -> outputs [(1,10), (2,20), (3,30)]
    
    As you can see, it takes the first item in the collection and joins it with the first item of the other collection, then the second with the second,
    so on so forth.
    
For more information on zip():
https://www.programiz.com/python-programming/methods/built-in/zip
    
reduce()

    Unlike the other methods described in these notes, the reduce() function is not built into Python and must be imported from a module.
    You would do so like this: 
    
        from functools import reduce
        
    Now, what is the purpose of the reduce function? Reduce() takes a series of values and will keep a running total until the total is reduced to a
    single value. The way it does this is by performing some form of operation on the values and combining them with the running total. 
    
    Imagine you need to see how many times a value shows up in a list, you can use reduce to find this out:
    
    def equals_five(total, value):
      if value == 5:
        return total+1
      else:
        return total

    my_list = [1, 4, 5, 5, 6, 10, 5, 9, 1, 3, 4, 5, 8, 5, 5, 5]
    count = reduce(equals_five, my_list, 0)
    print(count)
    
    reduce takes 3 parameters, the "accumulator" (the function that acts upon the items), the items (my_list in this case), and a value to start its
    running total at.
    
For more information on the reduce() function:
https://www.pythontutorial.net/python-basics/python-reduce-list/

Link to Repl.it demonstrating map(), filter(), zip(), and reduce():
https://replit.com/@AutomationApe/Functional-1

Lambda expressions

    Lambda expressions in Python are one time anonymous expressions. Lambda expressions are very useful in cases that you are need a function just
    once. 
    
    Imagine you need to return some numbers multiplied by 2, just once in your program. Rather than write a function for it, you could write a lambda
    expression instead:
    
        print(list(map(lambda item: item*2, my_list))) -> returns a list with the products of your original list items * 2
        
    This is memory efficient as no function has to be saved, the program runs the lambda expression when needed and then discards it once used.
  
For more information on lambda expressions:
https://www.w3schools.com/python/python_lambda.asp

Link to Repl.it demonstrating lambda expressions:

List Comprehensions

    Comprehensions are a quick way to create list/sets/dictionaries in Python instead of looping or appending a bunch of items to a list.
    
    Instead of doing:
    my_list = []
      for char in "hello":
        my_list.append(char)
        
    We could do:
    my_list = [char for char in "hello"]
    
    Using comprehensions, we can also fill a list with the results of an expression, ex:
    my_list2 = [num**2 for num in range(0,100)] -> this creates a list of all numbers from 0 to 99 to the 2nd power
    
    We can even use if statements in comprehensions. Let's say we only want the even squares of numbers between 0 to 99:
    my_list3 = [num**2 for num in range(0,100) if num % 2 == 0]
                      
For more information on list comprehension:
https://www.w3schools.com/python/python_lists_comprehension.asp

Set/Dictionary comprehensions 

    With Set comprehensions, it follows the same format as list comprehensions, just swapping out the [] for {}
    ex:
    
    my_set = { num ** 2 for num in range(0,101)}
    
    for dictionaries, since they are key-value pairs, it is a little different. The 
    ex:
    
    simple_dict = { "a" : 1, "b": 2 }
    my_dict = {key:value**2 for key,value in simple_dict.items() if value%2==0} -> outputs {"b":4} since we only want to see the even results of our
                                                                                   key:value pairs in the dictionary
                                                                                   
    We can also create key-value pairs from a list using dictionary comprehension:
    my_dict2 = {num:num*2 for num in [1,2,3]} -> outputs {1: 2, 2: 4, 3: 6}
        
