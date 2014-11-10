# SM-808 Practice exercise

The goal of this exercise is to practice designing models,
interfaces and defing APIs.

There aren't good or bad solutions, there are solutions that
match the requirements and some that don't. There are solutions that
might be considered elegant by some and solutions that would be
considered clever.

Feel free to use any programming language/framework you fancy, I'm personally curious to see submissions in [elm-lang](http://elm-lang.org/), [elixir](http://elixir-lang.org/) or [rust](http://www.rust-lang.org/).
I've already receieved awesome submissions in Ruby, JS, Angular.js, Rust and Go.
If you are applying for a job at Splice note that submissions in Go, js/Angular.js, Objective-C/Swift and C# are preferred.

## Building a Drum Machine

This exercise assumes you are somewhat familiar with drum machines. 
If you aren't
please read http://en.wikipedia.org/wiki/Drum_machine

Your challenge is to code the sequencer part of our Drum Machine which
we called SM-808. More precisely you will need to sequence and "play"
your own version of the famous [four-on-the-floor](http://en.wikipedia.org/wiki/Four_on_the_floor_(music)) rythm pattern.

![Example pattern to implement](/Four_to_the_floor_Roland_TR-707.jpg?raw=true)

Note that instead of hearing an actual sound, you are expected to
generate a real time visual representation of the sequence being played.

### Expected output

Here is some pseudo code showing the expected interaction and one way to
represent the output (you are encouraged to find a better way).
You can use a command line output, work in the browser or send use an electric circuit.
Use whatever programming language you want, as long as we can execute your solution.

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

![Output example](/drummachine-kata.gif?raw=true)

(ignore the audio outputs print at the beginning but pay attention to
the output speed at a BPM of 128)

If you decide to generate an output, [here is how the example pattern played on a tr-808 at 128 BPM](https://drive.google.com/file/d/0Bx7t4b0VA8_1Nkdhanowd3d5aEU/view?usp=sharing).

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
* The output isn't expected to be in sync with the tempo/BPM (bonus points if you manage to do it).


### Timing information

Outputing the patterns in tempo isn't required for this exercise, 
however if you wish to do so you might need some extra information.
At a 4/4 time signature of 60 BPM (beats per minute), we get 1 beat per second.
We can assume that 8 steps = 1 bar, representing 4 beats.
In other words, a 8 step pattern would take `(60/BPM)*4` seconds to play and each step would take `((60/BPM)*4)/8` seconds.


### Extra mile

* Try mix and matching patters of different durations (8, 16, 32 steps),
  note that if you have 2 patterns, one 8 and one 16, the 8 should play
  twice while the 16 plays once.
* Add support for velocity (the amplitude/volume of a note).
* Try to output sound (OS X has the `say` command, windows as `ptts`,
  also most language have bindings for [portaudio](http://www.portaudio.com/)

If you can't stop:

* How about live play? Can you allow users to add/remove/change patterns
  while playing?
* Make it even more interactive and add a web interface/GUI.


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


### Submit your solution

If you want your solution to be reviewed you can:

* email me your implementation as a zip or link to your repo (for candidates we are interviewing only)
* fork this repo and send a PR (community reviewed)
* create an issue with the url for your implementation (community reviewed)
