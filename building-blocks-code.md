## Building Blocks of Code

In today's class, we learned about the four building blocks of code: functions, variables (memory), `if` statements (conditions), and `while` loops.

### Translating from Pseudo-code

Last week, we used "fake code" to write our programs. This week, we "upgraded" to JavaScript, which has many more parentheses `()`, curly braces `{}`, and semicolons.

More about each building block soon, but here's how to translate concepts from "fake code":

<table>
  <thead>
    <tr><th>pseudo-code</th><th>javacsript</th></tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <pre>down
down
down
right</pre>
      </td>
      <td>
        <pre lang="javascript">down();
down();
down();
right();</pre>
      </td>
    </tr>
    <tr>
      <td>
        <pre>recipe downThreeTimes
| down
| down
| down</pre>
      </td>
      <td>
        <pre lang="javascript">function downThreeTimes() {
  down();
  down();
  down();
}</pre>
      </td>
    </tr>
    <tr>
      <td>
        <pre>if getColor is red
| down
| down</pre>
      </td>
      <td>
        <pre lang="javascript">if (getColor() == "red") {
  down();
  down();        
}</pre>
      </td>
</tr>
    <tr>
      <td>
        <pre>if getColor is red
| up
else
| down</pre>
      </td>
      <td>
        <pre lang="javascript">if (getColor() == "red") {
  up();
} else {
  down();        
}</pre>
      </td>
    </tr>
    <tr>
      <td>
        <pre>repeat if getColor isn't red
| down</pre>
      </td>
      <td>
        <pre lang="javascript">while (getColor() != "red") {
  down();
}</pre>
      </td>
    </tr>
    <tr>
      <td>
        <pre>save getColor as firstColorSeen</pre>
      </td>
      <td>
        <pre lang="javascript">var firstColorSeen = getColor();</pre>
      </td>
    </tr>
    <tr>
      <td>
        <pre>setColor remember firstColorSeen</pre>
      </td>
      <td>
        <pre lang="javascript">setColor(firstColorSeen);</pre>
      </td>
    </tr>    
  </tbody>
</table>

Now, the four building blocks as they appear in JavaScript:

### Functions

A function is like a recipe. It describes what sequence of actions to take in order to get some desired result. Functions can be built-in, like `down`, `up`, `left`, and `right` in the Rudy the Red Dot puzzle game.

Getting the robot to run a recipe is pretty simple: in parentheses `()` after the function name, tell it what parameters to use. If ther are no parameter, leave the parentheses empty, but *don't omit the parentheses* or you'll just be referring to the recipe, not telling the computer to actually execute the recipe. For example:

- `down;` -- tells the computer "hey, remember the function we called `down`?"
- `down();` -- tells the computer "hey, remember the function we called `down`? **RUN IT**"

The simplest functions are sequences of single built-in functions. For example:

```
function downThreeTimes() {
  down();
  down();
  down();
}
```

The `downThreeTimes` function executes the `down` function three times; it's pretty basic. But remember, this is telling Rudy *how to run* the `downThreeTimes` recipe, it doesn't *tell Rudy to run the recipe*. To run it, you'd need to add `downThreeTimes();` to your code.

### Memory and Variables

Memory is stored in the equivalent of a table. It might look something like this:

| name  | value  |
| ----- | ------ |
| color | "blue" |
| steps | 3      |

You can create new entries in the vable using the `var` keyword, like these two lines, which create the memory table above:

```
var color = "blue";
var steps = 3;
```

We didn't discuss `var` much in class, but you only need it the first time you use a variable. If you read the variable or update the variable later, leave off the `var`.

A super common use of variables is to store a value for later use. For example:

```
down();
var c = getColor();
down();
right();
setColor(c);
```

The `getColor` function, gives us back a "color" that we are storing in the variable named `c`. Then, later, the `setColor` function uses `c` as its color parameter.

Rememeber that setting a variable to the result of some function doesn't set up any kind of pemanent relationship: that function is run once, and the value you get back at that very moment is then saved in memory.

### `if` statements

`if` statements let you control the flow of your code so that it doesn't just sequentially run every line of code you have. The typical `if` statement might look something like this:

```
if (getColor() == "blue") {
  up();
} else {
  down();
}
```

The `else` branch is optional. The curly-brace characters, `{}`, enclose all the lines of code that are part of the **true** or **false** branches of the `if`.

### `while` loops

`while` loops are like repeated `if` statements. In other words, if the condition is true, not only is the body run, but the loop repeats itself and checks the condition again. A typical `while` loop might look something like this:

```
while (getColor() != "red") {
  down();
}
```

By combining a while loop with some memory, you can keep track of the number of times something has happened, and thus easily repeat a block of code a given number of times. For example:

```
var steps = 0;
while (steps < 8) {
  down();
  steps = steps + 1;
}
```

Whew. That's all we did today! If you're stuck on anything, ask a fellow student or email [me](mailto:jzamfirescupereira@cca.edu)!