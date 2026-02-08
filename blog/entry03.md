# Entry 3
#### 02/02/2026 - 02/07/2026

Hello! My last blog was a bit messy. It didn't feel like I described my thinking process clearly and felt rushed (because it was kind of rushed), so I'll try my best to describe it this time. Lately, I've been thinking about how the layout of my game will be. In the past two blogs, there was one that was a `runner`, basically meaning the character is only moving to the right, left, and jumping, while the other one I made in blog two allowed the `player` roam around the map. And while Runner seems cool, I feel like `RPG` would feel right. In this case, I'm going to be looking at the `Kaboom.js` playground and breaking down the code in a way I can understand it and do it my way. All my previous work will be commented out to start fresh. NOW FAIR WARNING, I USED CHATGPT (ohh nooo), but not to do my thing, but rather to explain any questions I had, it was that, or I looked at `kaboom` examples.

### Understanding the rpg style game

When looking at RPG YouTube videos and even the `kaboom.js` example, they had this new topic called `const levels, ` and I didn't really get, there was so many symbols like the one below:

```
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


```

Now, for this part, I had to ask ChatGPT to guide me towards the answer to what it was. Chat-GPT said something along the lines of not making the `leve`l but the `data`. IN MY OWN WORDS, imagine you're going to build a house, you won't figure out how you're going to build the house along the way of making it, you're going to NEED a plan, a `blueprint`, that's basically `levels`. If you notice in the levels, they have brackets because they are `arrays` containing the `blueprint`. `Levels` are the blueprint or data on how the structure of the house is going to look like and thats why you see `=` in almost a house type of form because it can represents the structure, and something that i learn is that it doesn't have to be a equal sign, it can be `@, #,$` or even `*`, it means something once you define it, like a v`ariable.` The `symbols` within can represent anything as long as you give them something to represent, and all of this is within multiple `brackets` because it's an `array`.

Another thing i want to mention, after creating the blueprint, we move on to the actual making. Something i notice in other examples of `levels` and `kaboom`, kaboom had this piece of code:

```
	const level = addLevel(levels[levelIdx], {
		...
	}
```
In this piece of `code,` we are now bringing back the `const level` earlier, and giving it's `value` for the `symbols`. Now it took to me a bit to follow a pattern to understand what was the purpose of `levelIndx`. `Indx` itself is `Index`, which basically are how we count `arrays`.


```
// normally we would count like
			 1 2.3 4
let array = [1,2,3,4]

but in array we have to count
			 0 1 2 3
let array = [1,2,3,4]
```

We are not counting the things within the `array`. we are counting where they are located. And how does this connect back to the topic? Basically, when we have multiple levels like in the `kaboom.js` example, we need `levelIndx` because it indicates what `level` we are in. so if there are `4 levels`, we are going to start at `level 0`, which is the level.

```
	const levels = [
						Although this array contains 3 levels, we are counting where they are located in the array so we use Index.
		[
			"===|====",
			"=      =",			// level 1
			"= $    =",
			"=    a =",			// levelIndx0
			"=      =",
			"=   @  =",
			"========",
		],
		[
			"--------",
			"-      -",
			"-   $  -",			//level 2
			"|      -",			//LevelIndx1
			"-    b -",
			"-  @   -",
			"--------",
		],

		[
			"=======--=======",
			"=              =",
			"=				========="
			"=						-"		//level 3
			"=				========="		//levelIndx2
			"=
			"=				="
			"================",
		]
	]
```


Since I'm getting started, I won't be able to make multiple levels just yet. My blueprint looks something like this:

```
 const levels = [
      [
        "=================    ========",
        "=               =    =      =",
        "= a             =    =      =",
        "=      b        ======      =",
        "=                           =",
        "=   $                       =",
        "=                           =",
        "====    =====================",
        "   =    =  ",
        "   =    =  ",
        "   =    =  ",
        "   =    =  ",
        "   =    ============",
        "   =                ",
        "   =                ",
        "   =================",

      ]
    ]
```

(ooooh so advanced)

Within the `const level = addlevel[0]{}`, we start adding the `width` and `height` of the walls and adding `value` to the `symbols` in the blueprint.

```

loadSprite("wall", "images/cobblewall.jpg");

addLevel(levels[0], {
        tileWidth: 64,
        tileHeight: 64,
        pos: vec2(450, 64),
		tiles:{
          "=": () => [				// This is the part where we start adding value to the symbols, "=" being the wall of structure
            sprite("wall"),			   We use sprites to make them contain the value, the sprite is the image for the wall
            area(),
            body({ isStatic: true }), //This part of the code makes the sprite unmoveable, like an actual wall.
            anchor("center"),
          ],
		}
```

And it would look like this

![alt text](<Screenshot 2026-02-07 at 11.14.12 PM.png>)

As you can see, we have the walls, yay! But theres gap between the wall, and it's a very huge building. At first, I thought it was maybe the `area()`, but `area()` is the `invisible barrier` that allows objects to be collided. So i went to the `width` and `height`, and for this part, I was decreasing numbers until eventually the size fit well.
```
        tileWidth: 50,
        tileHeight: 50,

```
Until it came out like this


![alt text](<Screenshot 2026-02-07 at 11.43.07 PM.png>)



Another thing to mention is when you give value to the symbols within the `const levels`, the things will spawn within that level, like I'm going to give value to `$` which is my `player` within the `const leve`l:


```
 		 "$": () => [
            sprite("flash"),
            area({width:1,height:1}),
            scale(0.5),
            body({ isStatic: false}), // this is turned off because I want this sprite/the player to be able to move around the map
            anchor("center"),
           ]
```

And the outcome would be:

![alt text](<Screenshot 2026-02-07 at 11.54.46 PM.png>)


### Take Aways

Although it didn't seem to be much of a blog, I felt like I really just took the opportunity to understand what each piece of the `kaboom.js code `can do. I still have many things planned, I want it to be something like the` kaboom.js`, where there is more than `one level`, add `movement` to the character, and where the camera moves with the user, like a collaboration between my 2 blog, where I added `Ai` that attacks. But right now I’m trying to set a steady `foundation` on the `JavaScript` I have right now. Some takeaways are to have add-on questions if that makes sense. When I said I used Chat-GPT, I always made sure that I wasn't asking it to do my work, but helping me to get an answer where I can understand and use by myself. That's all I have for this blog. Have a peppermint day!

[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
