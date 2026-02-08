# Entry 3
#### 02/02/2026 - 02/07/2026

Hello! My last blog was pretty messy, it didn't feel like i describe my thinking process straight and felt rushed (because it was kind of rushed) so I'll try my best to describe this time. Lately I've been thinking on how the layout of my game will be. In the past two blogs, there was one that was a runner, basically meaning the charcter is only moving to the right, left and jump while the other one i made in blog two, allowed the player roam around the map. And while runner seems cool, I feel like rpg would feel right. In this case I'm going to be looking at the Kaboom.JS playground and breakdown the code to a way i can understand it and do it my way. (All my previous work will be commented out to star fresh). NOW FAIR WARNING, I USED CHATGPT (ohh nooo), but not to do my thing but rather to explain any questions I had, it was that or i looked at kaboom examples.


### The start

When looking at rpg youtube videos and even the kaboom.js example, they had this new topic called ‘const levels‘ and I didn't really get, there was so many symbols like the one below:


‘‘‘
	const levels = [
		[
			"===|====",
			"=      =",
			"= $    =",
			"=    a =",
			"=      =",
			"=   @  =",
			"========",
		],
		[
			"--------",
			"-      -",
			"-   $  -",
			"|      -",
			"-    b -",
			"-  @   -",
			"--------",
		],
	]


‘‘‘

Now for this part I had to ask chatgpt to guide me towards the answer on what it was. Chagpt said something along the lines of not making the level but the data. IN MY OWN WORDS, imagine your going to build a house, you won't figure out how your going to build the house along the way of making it, your going to NEED a plan, a blue print, thats basically levels. If you notice on the levels, they have brackets because they are arrays containing the blueprint. Levels are the blueprint or data on how the structure of the house is going to look like and thats why you see = in almost a house type of form because it can represents the structure, and something that i learn is that it doesn't have to be a equal sign, it can be @, #,$ or even *, it means something once you define it, like a variable. The symbols within the 


[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
