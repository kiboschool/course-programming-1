# Elif

### If-elif statements

`if` and `else` let us express conditions with two possible outcomes. But what if there are more than two possibilities we want to express in our program? `elif` stands for "else if". It lets us check more conditions, so we can cover as many conditions as we want.

Below is the flow control diagram for a multi-branch program:

<div style="text-align:center">

![multi-way-flowchart](/lessons/conditionals/multi-way-decisions/multi-way1.png)

</div>

Here is the corresponding Python code:

```python
if x < y:
    print('x is less than y')
elif x > y:
    print('x is greater than y')
else:
    print('x and y are equal')
```

The code runs line by line. So, the conditions are checked _in the order the code is written._ The code does not look ahead. So, in the example above, assuming x = 3 and y = 3, the code will do 2 comparisons:

- Check if x is less than y. Since x = 3 and y = 3 this statement is false, and it keeps going
- Check if x is greater than y. Since x = 3 and y = 3, this statement is false
- Execute the else statement and print 'x and y are equal'

But with x = 4 and y = 6, the code will run the first comparison, print `'x is less than y'` and finish. It will never even run the second check!

There is no limit on the number of `elif` statements that can be added, but the code will evaluate them from top to bottom. Having an `else` statement is optional, but if you have one, it has to be at the end.

## Practice

<aside>

👩🏿‍💻 Let's get back to the party. Modify the code to account for whether or not there is free food.

</aside>

<img alt="free food flowchart" src="/lessons/conditionals/multi-way-decisions/free-food-flowchart.png" height="350"></img>

<iframe src="https://trinket.io/embed/python/42bc9d1f39" width="100%" height="300" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

The sample run of the code should now look like this:

![Sample run with elif statement](/lessons/conditionals/multi-way-decisions/elif-sample-run.png)

Nice!

![Snakes around a birthday cake](/images/snakes_with_cakes.png)
