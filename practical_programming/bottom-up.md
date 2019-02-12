## DRY - Don't Repeat Yourself. 
With this mindset, sometimes it's easy to get caught up in the thought that we need to write as little lines of code as possible. This shouldn't be the case, as less lines of code does not always mean better.

As programmers, we should use however many lines of code required to write the most efficient code that is robust, testable, and maintanable. When someone else sees our code, they should not be amazed at how little lines there are, but at how understandable it is for them, allowing them to continue with maintenance of the code.

> Less lines does not always mean better.

An example can be found in the difference between using top-down vs bottom-up approach to multiply numbers in range *1...n*.

### Top-down
This top-down approach recursively multiplies the numbers. Although it's only one line, the memory cost is *O(n)*. Depending on the size of *n*, it could possibly cause a stack overflow error (OOM - out of memory).

```python
def product_1_to_n(n):
    # We assume n >= 1
    return n * product_1_to_n(n - 1) if n > 1 else 1
```

### Bottom-up
Meanwhile, the code below takes a bottom-up approach. There are more lines, but the for loop takes smaller chunks of information (only what is necessary) and performs the multiplication operation. What is not needed is not stored in memory; thus, a max of *O(1)* memory cost is used for *O(n)* times - the loop runs *n* times, but each loop costs only *O(1)* space.

```python
  def product_1_to_n(n):
    # We assume n >= 1
    result = 1
    for num in range(1, n + 1):
        result *= num

    return result
```

### Less is not always more
From the examples above, the bottom-up approach uses double the amount of lines, but uses possibly considerably less memory cost (depending on how many big *n* is). 

Bottom-up is a good approach for when you have large amounts of data. By breaking the inputs down into smaller chunks, you are able to avoid running into OOM problems. 

**Resources:** [Bottom-Up Algorithm](https://www.interviewcake.com/concept/python/bottom-up?utm_source=drip&utm_medium=email&utm_campaign=Our+7+most+important+coding+interview+tips+%281+a+day+for+a+week%2C+unsubscribe+any+time%29&utm_content=A+trick+for+getting+good+at+coding+interviews+FASTER)
