> This section will present a ubiquitous real-world example of groups with the ultimate example of de-abstracting and demystifying the abstract and mysterious language that Group Theory stems from. This is good, because it'll be the only anchor to the place we call "the real world" in all 100-something pages of content. The rest rapidly devolves into insane and deranged statements such as "how is $t: \textbf{Fam}(\mathcal{A}) \to \text{Hom}(\mathcal{A, \mathbf{Enr(P)}})$ doing today?" or "the weather is pretty $O(2)\backslash\text{Isom}(SO(2))$ outside, don't you think?".

## Saga 1: The Horror of Hungary

> Pre"face", heh. Get it? Get it? <br/><br/>Please clap.

Everyone knows about the Rubik's Cube. It's fun, it's family-friendly,  it's one of the three most horrible things to come out of Hungary (the other two are Microsoft Excel and Viktor Orban); and, until Linux was invented in 1991, it was also the world's most effective diagnostic test for childhood autism. 

The intrigue of the Rubik's Cube lies in its reputation for being "easy to learn, impossible to master"; the exact same property that draws people to chess, or macarons, or Flappy Bird. So what makes it "easy to learn", and what makes it "impossible to master"? We observe four different properties of the Cube that perhaps explain both these aspects in tandem:

> <span style="background-color: #bc42f5; color: black;">Observation 1</span>. The Rubik's Cube only has six possible moves at any given moment: rotating any of the six faces clockwise. 

![alt text](./assets/images/image-48.png)

This requires just a tiny bit of extra elaboration. "But what about counterclockwise? WHAT ABOUT THE MIDDLE LAYER??", you say calmly. These moves are just as easily understood as combinations of clockwise rotations: for instance, the rotation of the horizontal middle slice anticlockwise is the rotation of the top and bottom faces clockwise. 

As such, every single permissible action - and every sequence of possible permissible actions, aside from the elusive "twisting the top-right corner clockwise when no one's looking" and the unsurpassable "hurling the Rubik's Cube towards my window at $v = 0.1c$ after missing my PB by 0.01 picoseconds" - can be described entirely by just six actions: $F, L, U, R, B$ and $D$.

> <span style="background-color: #bc42f5; color: black;">Observation 2</span>.  Every move is deterministic: you know exactly what will happen when you turn a face, barring minor accidents and unpreventable Acts of God.

The French horn is God's Instrument: when you play it, what's coming out the other side sounds either like a choir of angels singing a song of divinity or a constipated fart delivered by a 500-pound morbidly-obese man after two straight meals at Taco Bell, and only God knows which one it'll be. The Rubik's Cube is **not** God's instrument. You understand exactly what'll happen at any and every moment, and you also understand that

> <span style="background-color: #bc42f5; color: black;">Observation 3</span>. All moves are reversible, and

> <span style="background-color: #bc42f5; color: black;">Observation 4</span>. Moves can be freely combined in any order.

If you know precisely how a cube is scrambled - each and every rotation, in their rightful order, that had produced the state the cube is currently in - then you also know how to solve it: reverse all the steps, one at a time, until the cube is returned to its untouched, pristine state.

These four observations collect together to form our first understanding of what a group is.

> <span style="background-color: #03cafc; color: black;">Definition</span>. A **group** is a set of **actions** (moves) $G$, a **binary operation** (a means of combining such actions) $*$, and an **identity** ("do-nothing" action) $e$ satisfying the following four rules:
1. A combination of two actions $a$ and $b$, denoted $a * b$, is still a valid action that is a member of $G$. (This is true for any sequence of consecutive actions.)
2. Every action $a$ has its inverse $a^{-1}$, such that $a * a^{-1} = e$, the "do-nothing" action.
3. The "do-nothing" action $e$ does nothing: $a * e = a$.
4. Actions are **associative**: $(a * b) * c = a* (b*c)$.

In particular, we call the basic actions $F, L, U, R, B$ and $D$ - single clockwise rotations of the six faces - the **generators** of the group that describes the Rubik's Cube.
## Saga 2: Rubik's Platonic Solids

Rubik's Cubes come in all shapes and sizes. Some are cubes; some are pyramids. Some have numbers or faces on them. Some look vaguely pear-shaped, with a dull green color, a ring of metal around the top, and a sizzling sound alongside a vague smell of gunpowder - oh wait, silly me, I got confused with my WWII hand-grenade collection for a second. 

![alt text](./assets/images/image-50.png)

This is a (two-by-two) pyraminx. It is a two-hundred-gram hulking obelisk of nonbiodegradable plastic, lacking any bones, fat, and any connective tissue; an amalgamation of oceans upon oceans of liquified, strained, irretrievably destroyed, and artificially synthesized remnants of what was once purest crude oil in a past life. Its monolithic existence proves either that God is unaware of the horrors committed within his Kingdom, or impotent to intervene and stop them. But also you can turn it. 

(You might think even your 107-year-old great-great-grandmother with both Alzheimer's and Parkinson's could solve this. You would probably be right.)

There are certain similarities between a Rubik's Cube and a Pyraminx, beginning from the fact that both serve as the ultimate representations of mankind's declarations of war against the natural order. But also in how you can turn them.

> <span style="background-color: #bc42f5; color: black;">Observation 1</span>. **Rotational symmetries.** Four rotations of the same face for a Rubik's Cube gets you back to where you once was; a Pyraminx gets you there in three.

But perhaps slightly more intriguing is

> <span style="background-color: #bc42f5; color: black;">Observation 2</span>. **Commutativity.** Actions on a Pyraminx result in the same state when performed in any order; turning the top tip does not interfere with turning any of the other tips. This property does not generally hold for a Rubik's Cube.

A summary of the above two observations might go something like this. Both the (2x2) Pyraminx and the Rubik's Cube have certain symmetries; turning a face a certain number of times in a row reverts it back to its original state. These symmetries, however, differ wildly in their properties. A Rubik's Cube requires four turns to restore balance; a Pyraminx only three. A Rubik's Cube is non-commutative in general ($LLLL$ and $RRRR$, meaning left-face and right-face clockwise $90$-degree turns, both restore balance, and so does $LLLLRRRR$; but $LRLRLRLR$ results in something that looks a bit like a swastika and should generally be avoided), while a Pyraminx is not. 

(The two puzzles also differ slightly in their levels of complexity and their general target audiences: the Pyraminx has 256 possible configurations, while the Rubik's Cube has $43,252,003,274,489,856,000 .$)

Putting everything together:

1. **Groups involve symmetries.** The group for a Rubik's Cube is generated from the six fundamental actions, the clockwise turns of each face by $90$ degrees, that leave the cube unchanged - symmetrical - except for the colors; these actions can be combined in any order and freely reversed. Groups are a collection of ways to modify an object, such that the object remains the same in some way: a simple rectangle

    ![alt text](./assets/images/image-52.png)

    or a molecule

    ![alt text](./assets/images/image-51.png)

    and so on and so on. A **Cayley diagram**, like the one pictured above, is a neat way to describe the actions present in the group and how they affect the original object.

2. **Groups involve different types of symmetries.** For a Rubik's Cube, four face-turns are required to go back to the "do-nothing" symmetry; for a Pyraminx, the number is three. Some symmetries are commutative; others are not.

And thus we begin!