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
 A image example would look like this:

![alt text](<Screenshot 2026-01-15 at 10.38.02 PM.png>)



```
//Flash components
const Flash = add([
    sprite("The Flash"),
    pos(80, 200),
    scale(0.5),
    area(),
    body(),

])
```

The movement of the sprite at first was simple because I did it before but it was adding the moovement to move up and down.

```
//Flash movements
movement for the left
onKeyDown("left", () => {
    Flash.move(-SPEED, 0)
})
movement to the right
onKeyDown("right", () => {
    Flash.move(SPEED, 0)
})
movement to move up
onKeyDown("up", () => {
    Flash.move(0, -SPEED)
})
and movement to move down
onKeyDown("down", () => {
    Flash.move(0, SPEED)
})
```

Something interesting I noticed in the example from Kaboom is that if you look closely at the `Flash.move(0, -SPEED)` the arrangement of -SPEED is different, when moving sides to sides, the speed comes first, while moving up and down is last, also with negatives in moving left and down. The reason is the positioning. The grid in Kaboom is like geomotry, x and y, so it would be like this in geomtry terms `Flash.move(x,y)` as your moving to the right, the number will increase because of the position of the sprite, same thing when it down, the number will increase and oppsoite way around with left and down, the numbers will decrease.



Another thing I added was a enmeny ai that was a bot that used states, which says what is the sprite doing right now.

```
// Reverse Flash
const Reverse = add([
    sprite("The Reverse Flash"),
    pos(200, 200),
    scale(0.5),
    area(),
    state("move", [ "attack", "move"])
])
```
 Using this concept and the examples from kaboom I wanted to create two ai bots, one which was the reverse flash that would have two states, move which would follow the sprite (flash) and would attack, which would just stop him from moving. And the next sprite, captian cold was a what if sitution. What if i created a 2nd sprite that would always be in a attack state.


[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)



