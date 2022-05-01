Time for the good stuff, aka, the reason you are doing this course!

Before we jump into this, I need to make sure you understand the stack. 

# The Stack

The Stack is the fundamental underpinning of how memory works. It is complicated but you must understand it to move forward. We are going to watch a few videos until it makes sense. 

This explains the stack as a data structure: <https://www.youtube.com/watch?v=CgFVgp_VCN8>

This explains stack for memory: <https://www.youtube.com/watch?v=IWQ74f2ot7E>

And this finally explains what the hell it all means in regards to how programs work: <https://www.youtube.com/watch?v=Q2sFmqvpBe0&t=318s>

### Function Call Basics:

Read this, understand this, just keep going back over this until it all makes sense. This page is the single best reference for how programs actually work on the stack in existence.

<https://zhu45.org/posts/2017/Jul/30/understanding-how-function-call-works/>


# Overflows

Now that we understand the stack, let's learn how overflows work.

1. For an overview on overflows, watch this video: <https://www.youtube.com/watch?v=1S0aBV-Waeo&t=6s>
2. Watch [this video from LiveOverflow](https://www.youtube.com/watch?v=T03idxny9jE) that should help you understand the mindset required for overflows.

If you are still not feeling 100% sure what you are supposed to do, don't worry, that is perfectly normal. Just move on and work through these first couple of writeups.

### Crush Some Variable Overwrites

This variety of overflow is very easy to understand, so we start with variable overwrites. 

The core idea is very straightforward, a comparison is made against a variable the user is not expected to have control over, and using an overflow, we have overwritten that variable. Use the tools you've learned so far, especially Ghidra to figure out the write offsets. 

3. Do your first overflow! [Challenge 1](04-bof_variable/tamu19_pwn1/)
4. Next one up! [Challenge 2](04-bof_variable/tw17_justdoit/)
5. This one is a bit harder [Challenge 3](04-bof_variable/csaw18_boi/)

### Call some Functions

For this family of overflows, we'll be overwriting various addresses so that we can call target functions. 

6. Work through [Aviv's Overflow Notes](unit_03.md). Really take the time to get your head wrapped around these problems. 
7. Calling functions is pretty cool. [Challenge 4](05-bof_callfunction/csaw16_warmup/)
8. More CSAW challenges! [Challenge 5](05-bof_callfunction/csaw18_getit/)
9. Vulnchats are classic problems. [Challenge 6](05-bof_callfunction/tu17_vulnchat/)
 
# Historical Reading

Read this document ["Smashing the Stack for Fun and Profit"](http://www.phrack.org/issues/49/14.html#article) because it is famous. At the time this paper came out, the knowledge of the existence of buffer overflows was kept secret among a very small group of people. This is the first known document describing the dark magic that was released to the public. Now you are learning about it with a ton of examples on Github. Pretty dope.

# Shellcode 

Calling functions is nice and all, but you know what's better? Calling our own code! Let's learn about shellcode! 

0. Watch this video from LiveOverflow: <https://www.youtube.com/watch?v=HSlhY4Uy8SA>
1. Work Through [Aviv's Shellcode Notes Part1](unit_03_shell.md).
2. Do your first shellcode exploit. [Challenge 7](06-bof_shellcode/csaw17_pilot/)
3. Work through [Aviv's Shellcode Notes](unit_04.md). Take serious time on this. 
4. Do another. REPS AND SETS. [Challenge 8](06-bof_shellcode/tamu19_pwn3/)
5. Alright this one is a bit harder. [Challenge 9](06-bof_shellcode/tu18_shellaeasy/)

### Mitigations 

Let's talk mitigations! The world has decided it doesn't want overflows to be too easy since Aleph1 put out Smashing the Stack so plenty of things have been added to make our lives slightly harder. 

To figure out what mitigations are in place, use the "checksec" program. Once you figure out what is there, start thinking through how to defeat the specific mitigations. 

8. Read this [overview on a variety of mitigations](https://resources.infosecinstitute.com/topic/how-to-mitigate-buffer-overflow-vulnerabilities/)
9. Read this too, because why not? <https://ctf101.org/binary-exploitation/what-is-binary-security/>
10. Read this [writeup on canaries](7.1-mitigation_canary/readme.md).
11. Read this [writeup on ASLR and PIE](5.1-mitigation_aslr_pie/readme.md)
12. Read this [writeup on NX](6.1-mitigation_nx/readme.md)
13. Learn how to defeat some mitigations with [Aviv's Unit 5 Notes](unit_05.md)

Mostly, we are going to need to do some ROP, but that's for a later section.
