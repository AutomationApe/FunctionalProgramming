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
    
          
