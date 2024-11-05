# R functions

## Function overview

Functions in R are bundles of code that can be re-used. We have used many functions, which are marked with a following paranthesis, in this class. 


For additional details on functions see [Chapter 25](https://r4ds.hadley.nz/functions) in the R for Data Science textbook. The textbook states:

>> One of the best ways to improve your reach as a data scientist is to write functions. Functions allow you to automate common tasks in a more powerful and general way than copy-and-pasting. Writing a function has four big advantages over using copy-and-paste:

1. You can give a function an evocative name that makes your code easier to understand.

2. As requirements change, you only need to update code in one place, instead of many.

3. You eliminate the chance of making incidental mistakes when you copy and paste (i.e. updating a variable name in one place, but not in another).

4. It makes it easier to reuse work from project-to-project, increasing your productivity over time.

A good rule of thumb is to consider writing a function whenever you’ve copied and pasted a block of code more than twice (i.e. you now have three copies of the same code). 

## Writing R Functions

There are thee main components of an R Function:

1. A name. 

2. The arguments or inputs.

3. The body. Basic r code that is recreated.

Additionally, while not required, (4) documentation and (5) error handling are also important.

### (3) Function Body

This is the basic R code that would otherwise be copied-and-pasted.

__Exercise:__ Write code to randomly select a candy while trick-or-treating. Assume you are drawing from a bag with Reese's, Snickers, m&ms, and Kit Kats where there are equal probabilities for all candies.


### (1) Function Name

Recall the RouletteSpin function from last week and note the structure to define a function.

```
#| eval: FALSE
RouletteSpin <- function(num.spins){
  # function to simulate roulette spins
  # ARGS: number of spins
  # RETURNS: result of each spin
  outcomes <- tibble(number = c('00','0',
                as.character(1:36)),
                color=c('green','green','red','black','red','black',
                        'red','black','red','black','red','black',
                        'black','red','black','red','black',
                        'red','black','red','red','black',
                        'red','black','red','black','red',
                        'black','red','black','black','red',
                        'black','red','black','red','black','red'))
  return(outcomes[sample(38,num.spins,replace=T),])
}
```


```
#| eval: FALSE
name <- function(){
  
}
```

__Exercise:__ Select a name for your function. Similar to naming variables, this should be concise and meaningful. Verify your function works by running it.



### (2) Function Arguments

Function arguments are inputs into the body of our R code. They allow us to easily obtain different results without modifying the body of the code.

__Exercise:__ Add a function argument that enables you to select multiple candies from the trick-or-treat basket. Verify you function works by selecting 1, 5, and 10 candies.



### (4) Function Documentation

There are multiple ways to document functions. Here will use basic comments with the following structure

1. a one-sentence description; 
2. a list of the functions arguments, denoted by `Args:`, with a description of each and 
3. a description of the return value, denoted by `Returns:`. 
 
The comments should be descriptive enough that the function can be used without reading the function code.
 
__Exercise:__ Add these three documentation elements to your function.


 
### (5) Error / Warning Documentation

We have seen errors, warnings, and messages throughout the course.

`stop()` triggers errors and ends the function call. You should also enter descriptive text inside the function name to create an informative message.


__Exercise:__ Add a error message that catches cases where the user enters a non-numeric argument into your function. Hint: `is.numeric()` may be useful. Demonstrate that your error function works.


__Exercise:__ Add a warning message that catches cases where the user tries to take more than 5 pieces of candy..



---

Use your function, Monte Carlo principles, and data visualization skills to answer the following question:

1. Show the distribution of how many Reese's peanut butter cups you'd expect after visiting 10 houses.




2. Show the distribution of how many houses you'd need to visit to get your first Reese's peanut butter cup. Start by writing a function to calculate how many houses you visit to get a single Reese's

