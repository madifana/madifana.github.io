---
layout: post
title:  "Why I Need to Master Pry"
date:   2017-02-09 18:37:09 +0000
---

I recently created a CLI scraper program.  It was designed to scrape a stock screening website and display stocks that matched a predefined criteria.  The user could then select one of the stocks and receive more in depth information on it.  Starting with a good design layout this project should have taken me a day, or at most a week to complete.  

The first few hours in and everything was going great.  All the necessary files and folders were created and most of the code was laid out and working as it should be.  Suddenly there is an "undefined method" error.  No problem, the error is quickly located and corrected.  Just a typo on my part.  Now there is an issue with how many arguments are being passed into a method.  Easy enough fix, just forgot to add that in.  This goes on for about the next 3 hours.  Find an error, fix an error, and repeat.

At this point you might be tempted to say "So what? That's called programming", and you would be correct.  If the code isn't broken then it's finished.  However, after several days of "fixing" the errors that came up, I realized that they were the same errors I was getting before.  The only difference was that my pretty design layout was now ugly.  Methods didn't make sense anymore, they were located in the wrong files now, and what does that line of code even do?  Becoming very frustrated I took a step back, analyzed my situation, and decided to proceed in the most rational manner possible: continue doing what I've been doing until it works itself out.

Three weeks later, after having started from scratch twice and still ending up in the same position, I broke down and, hanging my head in shame, brought my program to an expert for assistance.  She looked over my code for a couple seconds, performed a binding.pry in a couple of places, then immediately started unbreaking things.  I knew pry could be used to test your code, but for the life of me I could never figure out how or why.  I played around with it a few times, mostly inserting it randomly into my code and then trying to figure out how the results should be helping me.

She explained everything she was doing as I watched intently.  At first I understood nothing, just nodded in agreement at everything she said so I didn't look stupid.  But as I watched and listened, everything slowly started making sense.  This entire time I had only been "fixing" the error that came up when I tried to run the program.  What I should have been doing was looking at what the application was suppose to be doing at the point when it broke and figure out why it wasn't doing that.  That is where Pry comes in.  You can use it to stop the program at certain points in your code to figure out where it is actually broken. Once you figure out what DOES work, you know what doesn't.  And THAT is the actual problem that needs to be corrected.

Any aspiring Ruby programmer that chooses not to use Pry is in for a long, frustrating road ahead.  This author is choosing the easy (easier) path and will be utilizing pry from this point on.


