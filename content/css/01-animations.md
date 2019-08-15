---
title: "Animations"
draft: false
---

An animation requires 3 thing:

-   The **start state** of the animation
-   The **end state** of the animation
-   **How long it should take** to go from start to end state (speed of the animation)

```css
* {
    /_there are 8 animation properties total_/
    animation-duration: 2s;
    animation-name: some-name;

    animation-iteration-count: infinite; /*number of iteration of the animation*/
    animation-timing-function: linear; /*changing the animation speed evolution*/
    animation-fill-mode: forwards; /*specify the style applied to an element when the animation has finished:*/
    animation-iteration-count: 4; /*numbero of iterations - can be infinite*/
    }
```

-   Define the animation

```css
@keyframes some-name {
    from { /*start state of the animation*/
        transform: rotate(0deg);
    }
    to { /*end state of the animation*/
        transform: rotate(360deg);
    }
}
```

If you require more frame, you can specify every step with a percentage instead of the `from` and `to` keywords.

* * *

## Animation Timing Function

To personalize the evolution of the animation, one can use the `cubic-beizer` function

```css
* {
    animation-timing-function: cubic-bezier(0.25, 0.25, 0.75, 0.75);
                                         /*(x1, y1, x2, y2)*/
}
```

This point represent the evolution of an animation vs time in a cartesian plane.
