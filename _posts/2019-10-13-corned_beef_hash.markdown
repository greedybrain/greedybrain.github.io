---
layout: post
title:      "Corned Beef 'Hash'"
date:       2019-10-13 23:43:47 +0000
permalink:  corned_beef_hash
---


So, I'm sitting here on this lovely morning with a cup of coffee and a bagel while reviewing some code that I've written. This piece of code includes some hashes - very important to getting this code to pass. As I'm reviewing it, I get so distracted from my hot cup of coffee which begins to cool down because I notice a very bad practice. I find that I wasn't being very descriptive with my iterations. 

I'm quite sure, and most can agree, that most of programmers tend to get lazy. Sometimes we get so trapped in thinking that we know exactly what we're doing that we half-ass things. The iterations through hashes for example. Say we call a '.each', or a '.collect' iteration method on a hash. Within the block of these methods you would usually see '|k, v|' (key, value) as placeholders. Yes, it's blatant that it's a certain key and value being passed, but what happens when the code futher within the body of the iterator becomes lengthy? What happens if the hash is an annoyingly nested hash? It'll become pretty tedious to track those 'k' and 'v's, and figure out which part of your hash is being referenced by those 'k' and 'v's.

Remember that 'being descriptive'  that I mentioned earlier? Well,  I learned that being descriptive with your placeholders, block arguments, what have you, can help you to be a more efficient programmer. And, in addition, you're not limited to only being descriptive when it comes to block arguments. Being descriptive throughout all of your code using comments, etc, is very good practice. Nested Hashes is just what I find to be my weakness at times.

Say we have a nested hash named avengers for size: 

	avengers = {
			 `code here`
	}
		
Within the avengers hash we'll have a few of our favorites along with some of their well known abilities, followed by what ability you think they should have in addition to what's already there.

	 avengers = {
				:iron_man => {
						 :abilities => ['intelligence', 'combat'],
						 :wished_abilities => ["nothing, hes good as is"]
				 },
				 :the_hulk => {
						 :abilities => ['strength', 'speed'],
						 :wished_abilities => ['wolverines claws']
				 },
				 :captain_america => {
						 :abilities => ['strength', 'combat'],
						 :wished_abilities => ['razor sharp ended shield']
				 }
	 }
		 
Now, let's loop through this hash and retrieve 'hulks'  wished abilities. This may be a pretty simple task, but the idea here is for you to see how descriptive I'm going to be about it.

		 avengers = {
				:iron-man => {
						 :abilities => ['intelligence', 'combat'],
						 :wished_abilities => ['nothing, he's good as is']
				},
				:the_hulk => {
						 :abilities => ['strength', 'speed'],
						 :wished_abilities => ['wolverines claws']
				},
				:captain_america => {
						 :abilities => ['strength', 'combat'],
						 :wished_abilities => ['razor sharp ended shield']
				}
	 }
		 
		 
**	 # THIS IS POORLY DESCRIPTIVE**


 ```
avengers.each do |k, v|
			puts "#{k} > #{v[:abilities]}" if k == :the_hulk
 end
```
		 
		 
**		 #THIS IS DISCRIPTIVE**
		 
	
	 avengers.each do |avenger, avengers_hash| (arg1 = the avenger, arg2 = avengers contents)
	      # puts out the abilities of the specific avenger
				puts "#{avenger} > #{avengers_hash[:abilities]}" if avenger == :the_hulk 
				
	 end


Badabang-badaboom! This along with other best practices will have you well on your way to being a expert programmer.


