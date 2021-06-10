# Randomized Wiggly Arrow Thingies!

Hooray!

# Why?
why not?

I wanted to do a mod where these wiggly arrows would appear eventually, however once I made all the code for them, actually doing the mod, draw the character (RIP Fiddle-chan), and connecting the stuff together proved to be very cumbersome. Since the code was already there, I decided *"why not give some of that juicy nightmare fuel to my fellow FnF redditors?"*, so I randomized the stuff and here we are now yaaaay.

# Extra unused features

The mod has custom JSON parsing, any note that has more than 3 attributes (`strumTime`,`arrowID`,`sustainLength`) will be considered to have 2 extra attributes: `cosWaveFrequency` and `dir`. These two determine the speed on which the note gets left, right and back on the screen (`0.5 cycles per second by default`), and the other if it's going to hit from the left or the right.

Since all the notes are hardcode-randomized that thing is... there. If the randomization is turned off you will see some experiments I conducted during development.

# Important pieces of code
* **Note.hx:**
  * Added extra attributes to calculate the position (also Note.hx now depends on FlxG for no reason yay)
  * The formula used is: `Math.cos( (remainingTime/1000)*cosWaveFrequency*Math.PI - targetAcos )` ~~*(will add formula demostration later)*~~
  * ***Demostration delayed, very**. In summary, there is cosine wave based on the time remaining for the note to get to the strum, this cosine wave is different for every strumline, as each one of them is offset by `targetAcos`, which, when `remainingTime` is 0, each yield the exact X position of the strum as it was originally intended (without any wiggle). `cosWaveFrequency` is just the speed at which it wiggles multiplied by `Math.PI`, which means that if its value were 2, the wiggling will occur at 1 Hz (1 cycle/second). Will further exemplify this later or in another repo, as I'm working on a mod rn. You know what that means, **prepare yourself**.*
* **PlayState.hx:**
  * Refresh the X position of the notes each frame.
  * Added custom JSON charting (unused).
* **FreeplayState.hx:**
  * Removed a thing that crashed FreePlay idk why.

# Issues
* ~~Senpai is dead I mean bugged~~ *\[Fixed. Kinda.\]*.
* ~~No distributable **yet**, you will have to compile the whole thing by your own means.~~
  * ~~ninjamuffin99's Funkin' repo explains how to do this in detail: <https://github.com/ninjamuffin99/Funkin#build-instructions>.~~
* Distributable available! Go to the [Releases](https://github.com/nikko-77/WigglyModFNF/releases) tab to download it!
* This is my **first ever** mod (in fact my first ever interaction with mods), sorry if something is off or missing idk how anything works pls don't kill me ;-;.
* I'm no good with git sorry if I mess up somewhere ;-;
* *I'm dang sorry ;-;*

Any helpful/constructive comments are appreciated :)