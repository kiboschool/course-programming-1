# Elif

_Estimated Time: 15 minutes_

---

![Snakes around a birthday cake](/images/snakes_with_cakes.png)

### If-elif statements

`if` and `else` let us express conditions with two possible outcomes. But what if there are more than two possibilities we want to express in our program? `elif` stands for "else if". It lets us check more conditions, so we can cover as many conditions as we want.

Below is the flow control diagram for a multi-branch program:

<div style="text-align:center">

![multi-way-flowchart](/future-proof-with-python/conditionals/multi-way-decisions/multi-way1.png)

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

![2%202%20Multi-way%20decisions%205adb8178795a43bf9ff453def27f562e/Screen_Shot_2021-07-27_at_3.10.10_PM.png](/future-proof-with-python/conditionals/simple-decisions/screen-shot-2021-07-27-at-3.10.10-pm.png)

Sample run of the code now look like this:

![2%202%20Multi-way%20decisions%205adb8178795a43bf9ff453def27f562e/Untitled%202.png](/future-proof-with-python/conditionals/simple-decisions/untitled-2.png)

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://replit.com/team/kibo-fpwp6/W23-Free-Food" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
