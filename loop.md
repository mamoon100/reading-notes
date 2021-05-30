# for statement
A for loop repeats until a specified condition evaluates to false. The JavaScript for loop is similar to the Java and C for loop.

A for statement looks as follows:

> `` for ([initialExpression]; [conditionExpression]; [incrementExpression]) statement `` 

When a **for** loop executes, the following occurs:

1. The **initializing** **expression** **initialExpression**, if any, is executed. This **expression** usually initializes one or more loop counters, but the syntax allows an **expression** of any degree of complexity. This expression can also declare *variables*.
2. The **conditionExpression** expression is evaluated. If the value of **conditionExpression** is true, the loop statements execute. If the value of **condition** is false, the for loop terminates. (If the **condition** **expression** is omitted entirely, the **condition** is assumed to be true.)
3. The **statement** executes. To execute multiple **statements**, use a block **statement** ``({ ... })`` to group those **statements**.
4. If present, the update **expression** **incrementExpression** is executed.
5. Control returns to Step 2


## Example
In the example below, the function contains a ``for`` statement that counts the number of selected options in a scrolling list ``(a <select>`` element that allows multiple selections). The ``for`` statement declares the variable i and initializes it to 0. It checks that i is less than the number of options in the ``<select>`` element, performs the succeeding if statement, and increments ``i`` by after each pass through the ``loop``.


# do...while statement 
The ``do...while`` statement repeats until a specified condition evaluates to false.

A ``do...while`` statement looks as follows:

> do
  statement
while (condition);

statement is always executed once before the condition is checked. (To execute multiple statements, use a block statement ``({ ... })`` to group those statements.)

If condition is true, the statement executes again. At the end of every execution, the condition is checked. When the condition is false, execution stops, and control passes to the statement following **do...while**.