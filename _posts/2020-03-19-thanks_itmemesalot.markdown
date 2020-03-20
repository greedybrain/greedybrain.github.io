---
layout: post
title:      "Thanks, ItMemesAlot"
date:       2020-03-20 03:59:20 +0000
permalink:  thanks_itmemesalot
---


**Project Introduction**

Hello, my name is Naya Willis. The rails project that I've done is called ItMemesAlot. It's a social media web application that curates Memes posted by many different individuals. This would be the typical flow, 1. A user would sign up, and then once logged in they will be redirected to their show page. On that show page, they'll have a notification section, and a posts section showing all of the posts that they've uploaded. 

**Authentication**

Three words for you, "I used Devise". Need I say any more?

**My Models**

My models include the following

1. User
2. Post
3. Comment
4. Like


A user is a person interacting with the application, such as uploading the meme, and commenting or liking a meme. The association is a user who has many posts, has many posts through likes, and comments. A post would be the actual meme, and it belongs to a user. It has many users through comments and likes and has many comments and likes. A comment is an interest left on a post and it belongs to a Post and a User. Lastly, a Like is also another way of showing interest. That model belongs to a Post and a User.

**My Controllers**

For each model above, I created a controller. I created the necessary actions in each controller to reflect the correct paths and direction throughout the use of the application. For example, I used a new and create action in the posts controller that enables a user to upload a post. It went a little something like this (with the user being logged in of course).

```
def new
	@post = current_user.posts.build
end
```

```
def create
	@post = current_user.posts.build(post_params)
	if @post.save	
		redirect_to user_post_path(current_user, @post)
	end
end
```

This is only part of what building this project entailed. Many other actions assisted in making this program run correctly and smoothly.

**My Views**

Certain actions required there be associated view templates. A new action required a new.html.erb file, a show action required a show.html.erb file, so and so forth. Throughout my view templates, I also utilized what you would call renders and partials with locals. You'll often see them used for forms, e.g. (`posts/_form.html.erb ==  <%= render "posts/form" %>`). Or, a partial, e.g. (`posts/_comment.html.erb == <%= render partial: "posts/comment, locals: { comment: @comment }" %>`). Then, I had a little fun with the styling part of it by using Tailwind-CSS which is a utility-first CSS framework. It is way less opinionated than Bootstrap!

**In Conclusion**

This project has been a blast to work on. I appreciate all that I learned so far with using Rails for Software Development. It's a very involved Web Framework, and I feel that I barely scratched the surface of all of the magic that it offers. Coming up, Javascript!
