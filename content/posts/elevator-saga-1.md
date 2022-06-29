---
title: "Elevator Saga: Part 1"
publishdate: 2022-06-29
slug: "elevator-saga-1"
description: "Elevator saga is a fun way to test your javascript skills"
keywords: ["elevator", "saga", "elevator saga", "javascript", "js"]
draft: false
tags: ["javascript", "elevator-saga", "algorithms"]
---

<!-- {{< figure src="/assets/elevator-saga/elevator.gif" alt="Elevator Saga" >}} -->



## Challenge 1

{{< highlight txt >}}Transport 15 people in 60 seconds or less (1 elevator, 3 floors){{< /highlight >}}

I'm going to start with a very basic algorithm and hopefully progress to something that resembles real-life elevator behavior.

In order to move the elevator, I need the `goToFloor` function (see the documentation [here](https://play.elevatorsaga.com/documentation.html#docs)). I'm going to start out by making an elevator that successively moves from the ground floor to the next floor and goes back to the ground floor when it reaches the top floor (Buddy the Elf-style).

<br/>
<div class="tenor-gif-embed" data-postid="7356021" data-share-method="host" data-aspect-ratio="1.92308" data-width="100%"><a href="https://tenor.com/view/elf-elevator-movie-pressall-gif-7356021">Elf Elevator GIF</a>from <a href="https://tenor.com/search/elf-gifs">Elf GIFs</a></div> <script type="text/javascript" async src="https://tenor.com/embed.js"></script>

I'll use the `on("idle")` event to start the elevator. Once it reaches the top and becomes idle, the event will fire again and the elevator will go back to floor 0.


{{< highlight js >}}
{
  init: function(elevators, floors) {
    var elevator = elevators[0]

    elevator.on("idle", function() {
      elevator.goToFloor(0)
      elevator.goToFloor(1)
    });
  },
  update: function(dt, elevators, floors) {
    // We normally don't need to do anything here
  }
}
{{< /highlight >}}

Great! That was a success. I won't show recordings of my elevator running, but you can copy the code and run it yourself. Smashing all of the elevator buttons seems to be working, let's try that again in Challenge 2.

## Challenge 2

{{< highlight txt >}}Transport 20 people in 60 seconds or less{{< /highlight >}}

Continuing on with the same approach from Challenge 1, I'm just going to send the elevator up to each floor (0, 1, 2, etc.) until it reaches the top. At that point the elevator goes back to the ground floor and starts over. In the real world, this would be a time and energy-intensive approach. Still,let's see if we can pass this challenge with this simple approach.

{{< highlight js >}}
{
  init: function(elevators, floors) {
    var elevator = elevators[0]

    elevator.on("idle", function() {
      elevator.goToFloor(0)
      elevator.goToFloor(1)
      elevator.goToFloor(2)
      elevator.goToFloor(3)
      elevator.goToFloor(4)
    });
  },
  update: function(dt, elevators, floors) {

  }
}
{{< /highlight >}}

Okay, that worked for me! It looks like there is some randomness and it won't necessarily pass every time with the same code.

## Challenge 3

{{< highlight txt >}}Transport 23 people in 60 seconds or less{{< /highlight >}}

All right, let's try our button-smashing technique one more time. I'm just going to use the same code as in Challenge 2.

{{< highlight js >}}
{
  init: function(elevators, floors) {
    var elevator = elevators[0]

    elevator.on("idle", function() {
      elevator.goToFloor(0)
      elevator.goToFloor(1)
      elevator.goToFloor(2)
      elevator.goToFloor(3)
      elevator.goToFloor(4)
    });
  },
  update: function(dt, elevators, floors) {

  }
}
{{< /highlight >}}

Okay, that may or may not work for you - it kind of seems like I'm hitting the limit of the button mashing technique. It failed on my first attempt, though. In the next post, I'll try out a new technique and start using different functions and events to hopefully make it more efficient.

What do you think? Let me know at chase@chase-mortensen.dev.

Chase