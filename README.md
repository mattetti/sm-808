# SM-808 Practice exercise

The goal of this exercise is to practice designing models and
interfaces.

There aren't good or bad solutions, there are solutions that
match the requirements and some that don't. There are solutions that
might be considered elegant by some and solutions that would be
considered clever.

## Building a Drum Machine

This exercise assumes you are somewhat familiar with drum machines. 
If you aren't
please read http://en.wikipedia.org/wiki/Drum_machine

Your challenge is to code the sequencer part of our Drum Machine which
we called SM-808. More precisely you will need to sequence and "play"
your own version of the famous [four-on-the-floor](http://en.wikipedia.org/wiki/Four_on_the_floor_(music)) rythm pattern.

![Example pattern to implement](http://en.wikipedia.org/wiki/Drum_machine#mediaviewer/File:Four_to_the_floor_Roland_TR-707.jpg)

Note that instead of hearing an actual sound, you are expected to
generate a real time visual representation of the sequence being played.

### Extra info

* A song contains multiple patterns being sequenced for different
  samples.
* A song plays at a given tempo (AKA bpm), the tempo does not need to
  be able change while the song plays.
* For this exercise, you are expected to implement 3 patterns for the
  following sounds/samples: kick, snare and
  hihat (you can use the example pattern or come up with your own).
* The time signature is expected to be 4/4 (if you don't know what that
  is, don't worry and ignore this instruction).
* The pattern is expected to be 8 steps or more.
* Your code will be executed on the command line or in the browser.
* Try to keep external dependencies to a minimum.
* See next section to see what to output.


### Expected output

Here is some pseudo code showing the expected interaction and one way to
represent the output (you are encouraged to find a better way).

```
// create a new song
song = Song -> bpm: 128, title: Animal Rights

// add the 3 patterns
song <- Kick   |X|_|_|_|X|_|_|_|
song <- Snare  |_|_|_|_|X|_|_|_|
song <- HiHat  |_|_|X|_|_|_|X|_|

song.play

// -> real time output
// |Kick|_|HiHat|_|Kick+Snare|_|HiHat|_|Kick|_|HiHat|.....
```

### Splice Evaluation

If you are given this exercise as a code challenge, we are going to
discuss a few things with you. In order to help you prepare, here is a
list of various specific parts and general aspects of programming we are
interested in discussing:

* How much time did you spend on the exercise, what parts took longer?
* What were the hard parts, what parts did you enjoy most?
* Data modeling - How did you model the concepts of songs and
  tracks/patterns, can you explain why?
* Simplicity vs Flexibility - How flexible is your solution? Can a user
  define patterns of different lengths? Can they play at the same time?
  Can the patterns be changed in real time? Can the velocity be set?
  None of these features are expected, what is needed for you to add
  support for these?
* Is your code tested? Why/why not? How would you test it (or better)?
