---
layout: post
title:  "Modifying the Devise Signup"
date:   2017-07-02 04:44:01 +0000
---


While creating my recent Rails Application, I decided to use devise for authentication.  Many Rails developers are very much against using devise, which is partly why I opted to try it.  This gave me an opportunity to gain a deeper understanding of it and put me in a position where I could draw my own conclusions.  Ultimately, I like how quickly you can get your initial authentications set up, but if you are creating a relatively simple program like I was, it can be a bit of an annoyance.  Especially if you need to add any custom fields.  All I wanted to do was add a "Username" to the signup view.  The following are all the steps I had to go through to do that...minus the hours spent figuring out what the steps were to begin with.

Starting at the beginning, I ran:

```
rails generate devise:views users
```

This brings up the devise users views in your views folder.  My first instinct here was to just add my changes to these new files, but that is not the way it works.  First you have to navigate to the 'config/initializers/devise.rb' file and find:

```
# config.scoped_views = false
```

and change it to:

```
config.scoped_views = true
```

I believe I found it on line 222, or somewhere around there.  This allows you to modify the views.  After that I had to run a migration to create the 'username' column in the 'users' table.  Simple enough, I would have to do that with or without devise:

```
rails g migration AddUsernameToUsers username:string
```

```
rake db:migrate
```

Now I could finally edit the 'views/users/registrations/new.html.erb' and add my username:

``` 
<div><%= f.label :username %><br>
<%= f.text_field :username, autofocus: true %>
</div>
```
			 
and that's it! Now that I've written all this down, it doesn't really seem like that much work...once you know what you're doing.  Hopefully this will help anyone trying to add custom fields to devise.  I personally think I'll keep using it.  Maybe as I delve deeper into the customization aspect of it I'll find issues, but for now I'm not against using devise.




