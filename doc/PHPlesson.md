#PHP lesson

##What is PHP, why is it different from Javascript?

**Server** and **Client**:
- The **client** is your browser -- it runs calculations on **your** computer.  Each person has a different computer, so they might see different things.
- The **server** is a computer in another city.  It stores the code that your browser is running, information in databases, etc.  The entire website runs on **one** server

Javascript runs on the **client** browser.  PHP runs on the **server**.

**Why do we need it?** We want to have a gallery that stores all the images that people have uploaded.  The server can remember all the images because every person who uploads an image uploads it to the same server.  If we used only Javascript, the server would not know of all the images that we uploaded.  So, we need PHP!

##Step 1: Make a PHP file

PHP can be integrated with HTML code like this:

> &lt;!DOCTYPE html&gt;  
> &lt;html&gt;  
> &lt;head&gt;  
> &lt;title&gt;My First PHP page&lt;/title&gt;  
> &lt;/head&gt;  
> &lt;body&gt;  
> &nbsp; &lt;?php  
> &nbsp; &nbsp;   
> &nbsp; ?&gt;  
> &lt;/body&gt;  
> &lt;/html&gt;  

Notice the **&lt;?php** and **?&gt;** brackets.

- **&lt;?php** will *start* a section of PHP code
- **?&gt;** will *end* a section of PHP code

Now **save** the file.  It can be anything but it needs to *end with* **.php**.

##Step 2: "Hello World"

Inside the PHP section, write this:

> &nbsp; echo "Hello World!";

Save it and **upload it**.  And see what the page looks like in the browser.

*You must upload the PHP file.  PHP is a server-side language so the code will only run if it is on a server.  Your computer is not a server, so it must be uploaded to a server to test it first.*

Find the **source code** once you see the page in the browser.

Now, **compare** the code you just wrote to the source code in the browser.

##Step 3: Array

Let's get some practice to get used to PHP.

Start of with a simple **variable**.

Remember in javascript we always start by declaring our variable like this: *var variable*?  PHP is different:

**All variables start with $** 

This code should create a variable, and display the contents.  Type the code into a PHP code section.

> &nbsp; $name = "John";  
> &nbsp; echo $name;  

**Task**: change the name to your name.

**Next, an array**

An array is a single variable that contains lots of data.  For example, the list of days in a week.  

Here's our goal: make an array called "days" that contains a list of all the days in a week.

There's actually multiple ways to do this: 

**Method 1:**

> &nbsp; $days = array(); // Let the computer know this is going to be an array, not a normal variable
> &nbsp; $days[0] = "Sunday"; // arrays always start at 0
> &nbsp; $days[1] = "Monday";
> &nbsp; $days[2] = "Tuesday";
> &nbsp; $days[3] = "Wednesday";
> &nbsp; $days[4] = "Thursday";
> &nbsp; $days[5] = "Friday";
> &nbsp; $days[6] = "Saturday";

**Method 2:** a bit of a shortcut with [].

> &nbsp; $days = array(); // Let the computer know this is going to be an array, not a normal variable
> &nbsp; $days[] = "Sunday"; // the [] means "add to the next available spot"
> &nbsp; $days[] = "Monday";
> &nbsp; $days[] = "Tuesday";
> &nbsp; $days[] = "Wednesday";
> &nbsp; $days[] = "Thursday";
> &nbsp; $days[] = "Friday";
> &nbsp; $days[] = "Saturday";

**Method 3:** Shortcut

> &nbsp; $days = array("Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday");

All of these do the same thing.  

**Next:** Display these days.

Again, there's multiple ways.  Type this **after** you define the array.

**Method 1:** Calling explicit elements of the array

The period actually means **add** -- it adds two words or characters together.

> &nbsp; echo $days[0] . "&lt;br /&gt;"; // Sunday  
> &nbsp; echo $days[1] . "&lt;br /&gt;"; // Monday   
> &nbsp; echo $days[2] . "&lt;br /&gt;"; // Tuesday   
> &nbsp; echo $days[3] . "&lt;br /&gt;"; // Wednesday   
> &nbsp; echo $days[4] . "&lt;br /&gt;"; // Thursday   
> &nbsp; echo $days[5] . "&lt;br /&gt;"; // Friday   
> &nbsp; echo $days[6] . "&lt;br /&gt;"; // Saturday   

**Method 2:** For loop

A for loop lets you repeat an action over and over again for a set number of times.  Let's start by looking at a simple for loop:

> &nbsp; for($i=0;$i<5;++$i)
> &nbsp; {
> &nbsp; &nbsp; echo $i . "&lt;br /&gt;";
> &nbsp; }

That first line is confusing.  It has 3 parts:

1. *$i=0*: start at $i = 0
2. *$i<5*: Keep repeating this loop as long as $i < 5. If $i is ever NOT < 5, then exit.
3. *++$i*: After you get through the loop once, increase $i by 1.

Here's what's happening in the computer:

> $i = 0.  
> echo 0.  
> $i = 1.  
>   
> [back to beginning of the loop]  
> is $i &lt; 5? 1&lt;5, so yes -- let's do the loop!  
> echo 1.  
> $i = 2;  
>   
> [back to beginning of the loop]  
> is $i &lt; 5? 2&lt;5, so yes -- let's do the loop!  
> echo 2.  
> $i = 3;  
>   
> [back to beginning of the loop]  
> is $i &lt; 5? 3&lt;5, so yes -- let's do the loop!  
> echo 3.  
> $i = 4;  
>   
> [back to beginning of the loop]  
> is $i &lt; 5? 4&lt;5, so yes -- let's do the loop!  
> echo 4.  
> $i = 5;  
>   
> [back to beginning of the loop]  
> is $i &lt; 5? 5 IS NOT less than 5, so EXIT.  

Okay **let's do it for the array**.

The 3 parts of the for loop:

1. Start a 0 (the first element of the array is 0): $i=0
2. Go up to the largest element in the array.  The largest element is 6, so $i&lt;7,  Or, more generally, $i&lt;count($days)
	- count($days) tells you how many elements are in the array "$days".  $days has 7 elements, so that is what we want.
3. As usual, add 1 at the end of the loop.

> &nbsp; for($i=0;$i<count($days);++$i)
> &nbsp; {
> &nbsp; &nbsp;
> &nbsp; }

So what is the code to go inside the loop?  We want to display all the days, so let's use $i=0 as an example:

> echo $days[$i] . "&lt;br /&gt;";

Now we just put that inside the loop

> &nbsp; for($i=0;$i<count($days);++$i)
> &nbsp; {
> &nbsp; &nbsp; echo $days[$i] . "&lt;br /&gt;";
> &nbsp; }

Upload it and check!
