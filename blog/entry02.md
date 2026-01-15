# Entry 2
##### 01/05/2024

Hello everybody, Since my previous blog, I would be tinkering here and there once in a while and today I will give an update on what I've been working on. So for context, from my previous blog, my 'prototype' game has been like a runner game. But one day I was thinking to myslef, yes my game is about the Flash a speedster well whole purpose is to run but there needs to be action so what if it would be just something like a freeroam game that would include a villian. So that's what I did, i commented out my other code to start new.

### Tinkering

Something that I enjoy about Ka-boom is that you can make mostly any type of game. For example in my previous blog I talked about how i created a runner game that would randomize the size of the pillars from around 150px to 310 in height to make it intresting, But thing about it is that it would get repetive and stricted movement to only move right and left and jump:



```
onKeyPress("space", () => {
    if (dog.isGrounded()) {
        dog.jump();
    }
});
onKeyDown("left", () => {
    // .move() is provided by pos() component, move by pixels per second
    dog.move(-SPEED, 0)
})

onKeyDown("right", () => {
    dog.move(SPEED, 0)
})
```
And with my vision of the game is to make it free roam, so you can move up and down and sides. I started by adding the fundimentals which is the speed and gravity, loading sprite and etc.

```
setup

kaboom()
CONST SPEED = 400
loadSprite("The Flash", "images/the_flash.jpg")
```
Also something that I notice when using http-server, normally I would just right click to inspect, expect in kaboom I can't so i went through the website and google and found a very helpful code, debug.


```
setup

kaboom()
CONST SPEED = 400
loadSprite("The Flash", "images/the_flash.jpg")
debug.inspect = true
```
It allows me to hover around the sprite and see the codes such as


```
    pos(80, 200),
    scale(0.5),
    area(),
    body(),
```
its helpful when eventually i add more collosion into the code with blocks and other things. With the sprite 



[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)



