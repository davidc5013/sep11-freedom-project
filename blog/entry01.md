# Entry 1
##### 11/26/2025


### Content

Hello everybody, this is my first blog as a junior for my `SEP11 freedom project`. I think at this point the readers will know the purpose of blogs and `Freedom Project`, but in case you don't, the `Freedom Project` is a whole year project where we get to choose a `tool` of code, in this case JavaScript, since I'm a junior and tinker with it to make something out of it. Now you may be asking I wonder what David's project is about? " Well, to that I say, I'm going to make a superhero game of the Flash, the fastest speedster in all comics and fiction.

#### The tool and tinkering

But how are you going to do that?" To that, I say I’m going to be using  <a href="https://kaboomjs.com/">kaboom</a>, a JavaScript program that helps make coding games easier and fun. I decided to use this tool rather than other gaming programs because, since my character is from comics and fiction, I found `Kaboom` to fall into that theme. One of the main ways I tinkered was by looking through the website and following the guide steps, and playing around. I spoke about this in my learning log, but in Kaboom, they use a `sprite`, which is the character of Kaboom called Bean:


![alt text](<Screenshot 2025-11-27 at 11.04.50 AM.png>)


But an issue that i notice is that when i tried `http-server` it just gave me a blank page or a page that says "bean is not found" and it took me TWO days like oh I don't have my own sprite called bean in my `IDE`, so why not make my own `sprite`, and I changed the `sprite` to my own, meet dog:


![alt text](<Screenshot 2025-11-27 at 11.24.41 AM.png>)

But the sprite is too huge, So i went around to `Kaboom-intro` and it showed different `components` such as a `scale()`, `area()`, `pos()`, etc. Scale helps controls the size of the sprite, so I was playing around the components

```
// initialize kaboom context
kaboom(

);
// load a sprite "dog" from the image folder
loadSprite("dog", "images/dog.jpg")

// adding the sprite to KABOOM
const dog = add([
    sprite("dog"),
    pos(80, 200),
    scale(0.2),
    area(),
    body(),
])
```

which resulted in:


![alt text](<Screenshot 2025-11-27 at 11.33.27 AM.png>)



The following steps was adding `platforms` to make the `sprite` stand on.


```
add([
    rect(width(), 60), the width
    pos(0, height() - 60), the height of the platform, 48 is at the bottom of the screen, so anything for example, 100 it would be around mid screen
    outline(4),
    area(),
    body({ isStatic: true }),
    color(127, 200, 255),
])
```


![alt text](<Screenshot 2025-11-27 at 12.28.50 PM.png>)


I did some other tinkering, such as the pink pillars you see, those are like obstacles to make the game more interesting:


```
function spawnTree() {
    add([
        rect(48, rand(24, 64)),
        area(),
        outline(4),
        pos(width(), height() - 200),
        anchor("botleft"),
        color(255, 180, 255),
        move(LEFT, 240),
        "tree", // add a tag here
    ]);
    wait(rand(0.5, 1.5), () => {
        spawnTree();
    });
}
```

But the question is how is the player or I going to avoid it? Well, by jumping of course, and while there was the code, it wouldn't let me jump. So I had to ask one of my friends and classmates, Edward, to help me out, and it took us 5 minutes looking around the intro until we realized that I forgot to set the gravity, which was this piece of code, plus the jumping code that allows the user to jump:



```
setGravity(600)

onKeyPress("space", () => {
    if (dog.isGrounded()) {
        dog.jump();
    }
});
```

I started playing around with the gravity, and as the gravity increases, the sprite won't jump as high compared to when the gravity is low. But with this, it seems easy to avoid the obsetecles, so why not increase the obstacles' height?

```
function spawnTree() {
    add([
      // above here, the rect is the width I'm sure
        rect(100, rand(150, 310)), // It's here where you can change it, the rand() is randomizing the height from a range of 150 to 350
        area(),
        outline(4),
        pos(width(), height() - 200), // At first I thought it would be here where I would change the height and width
        anchor("botleft"),
        color(255, 180, 255),
        move(LEFT, 240),
        "tree", // add a tag here
    ]);
    wait(rand(0.5, 2.5), () => {
        spawnTree();
    });
}
```

And the outcome would be this:


![alt text](<Screenshot 2025-11-27 at 1.04.10 PM.png>)




I wanted to add more movement then just jumping so I went to tutorials of movements to see:

```
onKeyDown("right", () => {
	dog.move(SPEED, 0)
})


onKeyDown("left", () => {
	dog.move(SPEED, 0)
})
```

I noticed something interesting: when you look at the movements and the jumping, they use two different variables. The jumping movement is `oneKeyPress`, while moving side to side uses `oneKeyDown`. That made me ask, “What’s the difference?” So, I tried changing them all to press. I found that for right and left, you have to press the key multiple times to move, which makes it harder, while for down, you just hold the key to move. I even tried this with the jumping movement, but it just remains the same.


### Ending

 Some takeaways is that a main reason why I sumbited my blog so late is that, I never really tinkered with anything because I didn't know where to start although the main source, <a href="https://kaboomjs.com/">kaboom</a> but It would have to be ask for help espically in person because don't get me wrong, theres a whole groupchat of classmates using Kaboom and we can ask people there, but it seems more productive if it was in person because you guys are in the same place, interacting with each other and thats what happen with me and my classmates. But thats all I got for this blog, thank you peppermint day.


[Next](entry02.md)

[Home](../README.md)
