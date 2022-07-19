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
    
      def multiple_by2(li):
        new_list = []
        for item in li:
          new_list.append(item*2)
        return new_list
        
      print(multiply_by2([1,2,3]))
     
    This is an example of functional code as it follows the rule previously stated rules. It will always produce the same results and does not affect
    the outside world.
    
    Pure functions create clean, safe code. * It is not possible to always create functional code, but when possible, you should *
    
    
    
          
