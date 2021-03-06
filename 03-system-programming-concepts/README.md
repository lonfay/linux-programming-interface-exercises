Chapter 03: System Programming Concepts
=======================================

Question 3-1
------------

**Question:**

When using the linux-specific reboot() system call to reboot the
system, the second argument, magic2, must be specified as one of a
set of magic numbers (e.g. LINUX_REBOOT_MAGIC2).  What is the
significance of these numbers? (Converting them to hexadecimal
provides a clue)

**Answer:**

```
~/Projects/OpenSource/linux-programming-interface-exercises/ch3 $ ./ch3_1
LINUX_REBOOT_MAGIC1 = 0xFEE1DEAD (-18751827)
LINUX_REBOOT_MAGIC2 = 0x28121969 (672274793)
```

The magic numbers are not present for most function calls but to
prevent erroneous calls to reboot (let's say that the pc just happened
to go to this code, we want some addititional security).  The numbers
themselves (in hexadecimal) each have clever meaning:

 - 0xFEE1DEAD: Feel Dead?  Self-explanatory.
 - 0x28121969: 28th of December 1969 is the birthday of Linus
   Torvalds!
