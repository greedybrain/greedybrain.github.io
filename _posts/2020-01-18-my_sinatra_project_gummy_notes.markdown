---
layout: post
title:      "My Sinatra Project Gummy Notes"
date:       2020-01-18 15:55:18 +0000
permalink:  my_sinatra_project_gummy_notes
---

So, at last, my project is complete. Oh, what a wonderful experience developing this project has been. My Sinatra project is called Gummy Notes. Gummy Notes is a  web app where you can keep track of tasks and reminders. It's sort of like a Todo list, but the only difference is that you're using color-coded digital sticky notes, rather than a row by row list of text-based todo's.

We were tasked to create our Sinatra projects using CRUD functionality along with some User Authentication. I approached the User Authentication part first. Along with user authentication, I also ensured that sessions worked correctly as well. Though user authentication required gems such as Bcrypt, other known gems also assist in the authentication of a user. With Bcrypt it allowed me to use the method '.authenticate' on my user instance. This method checked if a user's username and his/her encrypted password match. From Google itself, "bcrypt() is a sophisticated and secure hash algorithm designed by The OpenBSD project for hashing passwords. The bcrypt Ruby gem provides a simple wrapper for safely handling passwords". Here's a look at my signup, and login screens.

Signup

http://sinatra-gummynotes.herokuapp.com/signup

Login

http://sinatra-gummynotes.herokuapp.com/login

Next up, sessions! By enabling sessions in my "configure do" block and then setting a session secret I can track and confirm the authenticity of a particular user throughout their use of the application. It looks a little something like this ...

```
configure do 
        set :views, "app/views"
        set :public_folder, File.join(APP_ROOT, "public")
				
        enable :sessions
        set :session_secret, "secret_here"
end
```

Once the user authentication is setup correctly and a user is finally logged in they can create a gummy note by clicking the plus button or the button that reads "Create your first gummy note". After the note is created it is posted via the form post method to the users home page which displays all of their notes. Once a user creates a note it can then be edited, deleted, and viewed in-depth(show action). One additional feature I added was the delete to trash bin. This was a little challenging to accomplish because I was so wrapped up on it being a complete delete action that all I had to do was set the notes user to nil so that it would be unassigned from the user and to the users trash bin instead. 

```
def add_to_trash
            @note = GummyNote.find_by(id: params[:id])
            @note.trash = current_user.trash
            @note.trash.gummy_notes << @note
						@note.user = nil
            @note.trash.save
            @note.save
            redirect "/account/home"
end
```

Then the actual deleting will be from the trash bin when a user chooses to empty their trash bin. 

```
def empty_trash_bin
            notes = current_user.trash.gummy_notes.all
            notes.destroy_all 
            redirect "/account/home"
end
```

In conclusion, this project was a really in-depth project. I enjoyed it a lot, and learned a lot while doing it. I even did some refactoring which helped to solidify my knowledge of what I've been doing.
