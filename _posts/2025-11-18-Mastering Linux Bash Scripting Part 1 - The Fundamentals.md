-----
title : "Mastering Linux Bash Scripting: Part 1 - The Fundamentals"
date : 2025-11-18
categories : [Linux, Programming]
tags : [Linux, Bash, Scripting, Automation, Beginner's Guide]
-----

<img src="../assets/bash-scripting.png" alt="bash-scripting">

# Mastering Linux Bash Scripting: Part 1 - The Fundamentals

If you work with Linux, whether as a System Administrator, a DevOps engineer, or a Cybersecurity analyst, the terminal is your home. While you can type commands one by one, the real power of Linux unlocks when you start **scripting**.

This is **Part 1** of our Bash Scripting roadmap. In this article, we will cover the absolute basics: why we use it, how to create your first script, and how to handle data using variables.

## Table of Contents

1.  [Why Learn Bash?](https://www.google.com/search?q=%231-why-learn-bash)
2.  [The Shebang & Your First Script](https://www.google.com/search?q=%232-the-shebang--your-first-script)
3.  [Variables in Bash](https://www.google.com/search?q=%233-variables-in-bash)
4.  [Data Types: Strings vs. Numbers](https://www.google.com/search?q=%234-data-types-strings-vs-numbers)
5.  [Next Steps](https://www.google.com/search?q=%235-next-steps)

-----

## 1\. Why Learn Bash?

Bash (Bourne Again SHell) is the default command-line interpreter for most Linux distributions. Writing a script is essentially saving a list of commands to a file so the computer can execute them for you.

Here is why you need to learn it:

  * **Automation:** If you have to do a task more than twice, automate it. Bash is perfect for daily backups, system updates, or log cleaning.
  * **Universality:** Bash is pre-installed on almost every Linux server in the world. You don't need to install Python or Java to get things done.
  * **Speed:** For managing files and system processes, Bash is faster and more direct than writing a high-level program.

-----

## 2\. The Shebang & Your First Script

Before we talk about variables, we need to know how to make a file "executable."

Every Bash script starts with a specific line called the **Shebang**. This tells the system which interpreter to use to run the code.

### The Syntax

Create a file named `hello.sh`.

```bash
#!/bin/bash

# This is a comment. The system ignores lines starting with #
echo "Hello, World!"
```

### How to Run It

By default, Linux files are not executable for security reasons. You must grant permission first.

1.  **Make it executable:**
    ```bash
    chmod +x hello.sh
    ```
2.  **Run the script:**
    ```bash
    ./hello.sh
    ```

-----

## 3\. Variables in Bash

Variables are containers for storing data. Unlike languages like C++ or Java, Bash is very flexible with variables, but it is strict about **syntax**.

### Declaring Variables

**The Golden Rule:** There must be **NO SPACES** around the equal sign `=`.

  * ❌ `name = "John"` (This will fail)
  * ✅ `name="John"` (This works)

### Accessing Variables

To use the value stored in a variable, you must put a `$` sign in front of it.

### Example Script: `user_info.sh`

```bash
#!/bin/bash

# Defining variables
username="CyberUser"
role="Penetration Tester"
directory="/home/cyberuser/tools"

# Using the variables
echo "The user $username is working as a $role."
echo "Their tools are located in: $directory"
```

**Output:**

> The user CyberUser is working as a Penetration Tester.
> Their tools are located in: /home/cyberuser/tools

-----

## 4\. Data Types: Strings vs. Numbers

Bash is technically a "typeless" or "loosely typed" language. It essentially treats everything as a string (text) unless you force it to do math.

### 1\. Strings

Strings are just text. You should generally wrap them in quotes.

  * **Double Quotes (`""`):** Allow variables to be expanded.
  * **Single Quotes (`''`):** Treat everything literally (variables won't work).

**Example:**

```bash
name="Alice"

echo "Hello, $name"  # Output: Hello, Alice
echo 'Hello, $name'  # Output: Hello, $name (Literal string)
```

### 2\. Integers (Numbers)

Because Bash treats everything as text, `1 + 1` is just the text "1 + 1". To do math, we need special syntax.

We use double parentheses `(( ... ))` for arithmetic.

**Example Script: `math_test.sh`**

```bash
#!/bin/bash

num1=10
num2=5

# Incorrect way (will just print the text)
echo $num1 + $num2 

# Correct way (performs the math)
sum=$(( num1 + num2 ))
echo "The sum is: $sum"

# You can also do subtraction, multiplication, etc.
echo "Multiplication: $(( num1 * num2 ))"
```

-----

## 5\. Next Steps

Congratulations\! You've taken the first step. You now understand how to create a script, set permissions, store data in variables, and perform basic math.

In **Part 2**, we will make our scripts intelligent. We will cover:

  * **User Input:** Asking the user for data.
  * **Logic:** Using `if`, `else`, and `elif` statements.
  * **Loops:** Repeating tasks automatically.