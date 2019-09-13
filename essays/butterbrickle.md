---
layout: essay
type: essay
title: What makes a question a Smart one? 
# All dates must be YYYY-MM-DD format!
date: 2019-09-12
labels:
  - Smart Questions
  - Stack Overflow
  - Self Improvement
  - Life
---

What is a good question? I think we intuitively know the answer; if I showed you two questions, you could probably tell me which one was smart and which one was more ... intellectually simple. 

You've probably heard that when meeting people for the first time, we make a lighting fast decision about whether we like them or not. This is especially true on the esteemed dating platform, Tinder, a dating app where you accept/reject a person after judging them by a few pictures and a short bio. I think there's a comparison to be made between choosing a date and choosing a question; and in doing so, maybe we can find out what makes a question a smart one? 

Let's play a game of [StackOverflow](https://stackoverflow.com) Tinder, shall we? 

Start From the Top: 
--- 
In lieu of a picture; based on the title, which question would you choose? 

A: [Maximum number of components per activity Android](https://stackoverflow.com/questions/57919424/maximum-number-of-components-per-activity-android)
---

B: [Why is processing a sorted array faster than processing an unsorted array?](https://stackoverflow.com/questions/11227809/why-is-processing-a-sorted-array-faster-than-processing-an-unsorted-array)
---

First off, only B is actually a question; which implies it has an answer. "Question" A is a statement. It sounds like a google search - the author could just copy and paste it in. It sounds like something that would require you to ask a question for clarification. It sounds like extra work on your part, if you choose to accept it. 

B's title is specific, which I think makes it seem more approachable because you know what to do with this inquiry. The structure of B's title stears you to a future answer such as “processing a sorted array is faster because…”. You already know if your efforts are going to be worth anything because you can measure if you've answered the question. It is definitely getting off on the right foot!  


Let Me Explain...
---

Let’s say you decide to give them a chance and read their "bio". 

A: 
---
Is there a limit as to how many components an android activity can hold? And how does it affect the application's performance? Thank you.


B: 
---
Here is a piece of C++ code that shows some very peculiar behavior. For some strange reason, sorting the data miraculously makes the code almost six times faster:
```
#include <algorithm>
#include <ctime>
#include <iostream>

int main()
{
    // Generate data
    const unsigned arraySize = 32768;
    int data[arraySize];

    for (unsigned c = 0; c < arraySize; ++c)
        data[c] = std::rand() % 256;


    // !!! With this, the next loop runs faster.
    std::sort(data, data + arraySize);


    // Test
    clock_t start = clock();
    long long sum = 0;

    for (unsigned i = 0; i < 100000; ++i)
    {
        // Primary loop
        for (unsigned c = 0; c < arraySize; ++c)
        {
            if (data[c] >= 128)
                sum += data[c];
        }
    }

    double elapsedTime = static_cast<double>(clock() - start) / CLOCKS_PER_SEC;

    std::cout << elapsedTime << std::endl;
    std::cout << "sum = " << sum << std::endl;
}
```
 * Without std::sort(data, data + arraySize);, the code runs in 11.54 seconds.
 * With the sorted data, the code runs in 1.93 seconds.
 
 Initially I thought this might be just a language or compiler anomaly, so I tried Java:
 ```
 import java.util.Arrays;
import java.util.Random;

public class Main
{
    public static void main(String[] args)
    {
        // Generate data
        int arraySize = 32768;
        int data[] = new int[arraySize];

        Random rnd = new Random(0);
        for (int c = 0; c < arraySize; ++c)
            data[c] = rnd.nextInt() % 256;


        // !!! With this, the next loop runs faster
        Arrays.sort(data);


        // Test
        long start = System.nanoTime();
        long sum = 0;

        for (int i = 0; i < 100000; ++i)
        {
            // Primary loop
            for (int c = 0; c < arraySize; ++c)
            {
                if (data[c] >= 128)
                    sum += data[c];
            }
        }

        System.out.println((System.nanoTime() - start) / 1000000000.0);
        System.out.println("sum = " + sum);
    }
}
 ```
 with a similar but less extreme result.

My first thought was that sorting brings the data into the cache, but then I thought how silly that was because the array was just generated.

* What is going on?
* Why is processing a sorted array faster than processing an unsorted array? The code is summing up some independent terms, so the order should not matter.



Give enough context/info bc you might assume the problem is caused by one thing when it is in fact caused by something else. Another person would be able to find the actual problem bc they have enough info 
Respectful of peoples’ effort and time to help you (do them a favor); shows maturity 
Reciprocation 


Verdict:
---
Is it really a comparison? I think B is the better, smarter question. 

When you don't have the ability to talk to the person behind the bio, behind the picture, behind the question, you will only be able to analyse them by the pieces of information they release to the world. The construction of the question becomes the data by which you judge the person - and see if they are worthy of an answer. 


If anything, you can take a page from Eli the Computer Guy's playbook and just default to an equally contextless answer. 














