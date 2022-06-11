---
title: "Elevator Saga #1"
publishdate: 2022-06-11
slug: "elevator-intro"
description: "Elevator saga is a fun way to test your javascript skills"
keywords: ["elevator", "saga", "elevator saga", "javascript", "js"]
draft: true
tags: ["javascript", "elevator-saga", "algorithms"]
---
<br>

{{< figure src="/assets/elevator-saga/elevator.gif" alt="Elevator Saga" >}}

I discovered a new site called [Elevator Saga](https://play.elevatorsaga.com/) while listening to the [Stack Overflow Podcast](https://stackoverflow.blog/podcast/). It's a great site for testing your javascript skills in a fun way. Essentially, you are given progressively more difficult scenarios and have to program one or more elevators to carry passengers to different floors in a given time limit.

I am going to be working through each of these levels and sharing how I tackle each challenge. By the end, I'm hoping to have a decent working elevator program. If you're interested in writing your own program, you can find the API documentation [here](https://play.elevatorsaga.com/documentation.html#docs).


{{< highlight js >}}
{
    init: function(elevators, floors) {
        var elevator = elevators[0];

        elevator.on("idle", function() {
            elevator.goToFloor(0);
            elevator.goToFloor(1);
        });
    },
    update: function(dt, elevators, floors) {
        // We normally don't need to do anything here
    }
}
{{< /highlight >}}
