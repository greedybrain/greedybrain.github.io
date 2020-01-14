---
layout: post
title:      "Object Models as Metaphors"
date:       2020-01-14 04:03:28 +0000
permalink:  object_models_as_metaphors
---

When creating object models in a CRUD(Create Read Update Destroy) application, or even in a CLI(Command Line Interface) application, I like to think of it as mimicking the real world. You start to see your application playing in many different ways. It's sort of like a movie. A movie isn't a movie without characters who play a certain role that together with other characters and their roles shape out the entire movie.

Now, deferring from this analogy, and explaining this from more of a programmatic perspective. Say I was building an app similar to Facebook. Or better yet, let's just use Facebook in general. By now, I know enough to confirm that Facebook has a user model (along with thousands of other models). But, specifically speaking on the user, it would have that a user has a name, an email, and a profile image, simple enough right? A user can have so much more to them but you can already start to see a user being defined(modeled)  out with just the above attributes. 

You would now ask the question, what is the users' role? Well, on Facebook a user can do a lot. From creating a text post, uploading an image, or even uploading an image with a text post attached and a plethora of other things. All of this is what would go into a user's model, and would accumulate to Facebook's purpose; being social. 

As you can see, models help you get to the end goal of your application. I feel as if it bridges the gap between it and my views, or it and my controllers.  It's why I would prefer figuring out my models before thinking further ahead about my views and controller actions. And, in the case of CLI applications, it helps there as well.


