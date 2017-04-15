---
layout: post
title:  "SINATRA, Syntax, and Me"
date:   2017-04-15 22:17:15 +0000
---


I recently published a Ruby gem to RubyGems.org.  It is an app created to keep track of the books my son reads.  His teacher wants him to read at least one book a day, then write down every book he read and turn the list in to her every few months.  I figured this was the perfect opportunity to practice my Sinatra programming.  With this gem, every child can create their own password protected login, add or edit the books they read, delete books, and log out.  It also displays flash messages explaining any user errors while filling out forms.

The initial layout for this was fairly simple: 

app
   -controllers
	 -models
	 -views
db
   -migrations
	 
...and so on.  All the associations and routes were pretty straightforward.  I ended up with just 2 models: user and book.  A book belongs to a user and a user has many books.  Each controller was only given the basic Create, Read, Update, and Delete features.  The views were about as simple as I could make them, with titles on each page and explanations to fill out the forms.  

While programming all this out, I ran into a few simple syntax errors that almost doubled the amount of time required to complete the app.  On the surface, they are very simple typos with easy corrections.  What made it take so long to fix was that I could NOT find the errors to fix them.  Even when I ran shotgun and it told me EXACTLY where the error was, I went over and over that line of code and couldn't figure out why it was wrong.  The first error was this line of code:


```
if logged_in?
			redirect '/users/#{current_user.slug}'
else
```

Now I can pick out the problem in a heartbeat, but I went over this repeatedly and could not see anything wrong with it. Now I know it is this:


```
if logged_in?
			redirect "/users/#{current_user.slug}"
else
```


See the difference? I needed to use double quotes (" ") instead of single (' ').  The #{} operator is used for interpolation inside DOUBLE quoted strings.  Inside of a single quoted string, it is just read as a string.  Now, I would say this is a stupid mistake to make...except that a couple hours later I received an error for making the exact same mistake again...and I could not remember for the life of me how I fixed it the first time!  
