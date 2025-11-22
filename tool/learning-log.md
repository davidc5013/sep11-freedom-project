# Tool Learning Log

## Tool: Ka-boom

## Project: Video game about the flash

---

### 09/29/2025:
* Text

### 11/21/2025:
* Text
Hello hello, So this is my first learning log (yikes), but anyways, I've tinkering here and there, I think a main stumble in my tinkering was the "https://kaboomjs.com/doc/intro"  where  if you wanted to start anything, like character wise, it would have through a bean charcter, and i was like okay, well It doesn't matter cause i thought it would just download automotically when i inported the java script code (this one):

`import kaboom from "https://unpkg.com/kaboom@3000.0.1/dist/kaboom.mjs";`

but it didn't because when i copy this code from the website

```
// load a sprite "bean" from an image
loadSprite("bean", "sprites/bean.png")

// add something to screen
add([
    sprite("bean"),
    pos(80, 40),
])



```

It didn't work because of the fact, there was no folder or any inport of the `sprite` `bean`, so i was just left confused. Until one day I asked my friend Jason to help me out in that part, and he told me, "maybe you should make your own sprite" or something around those lines, but then It was like uploading a screenshot, but instead of a screenshot it would just be a image, so i would use a image from my personal laptop and the code would turn to something like this:


```
// load a sprite "bean" from an image
loadSprite("dog", "images/dog.jpg")

// add something to screen
// putting together our player character
const dog = add([
    sprite("dog"),
    pos(80, 560),
    scale(0.1),
])



```

<!--
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
