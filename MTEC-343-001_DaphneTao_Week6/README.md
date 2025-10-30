#wt-digital-Crickets Synth Compose
##code
```Javascript
setcpm(125/4)
$BASS:n("<0 -3 -2 -4>".add(-7)).scale("g#:minor").s("wt_digital_crickets")
.orbit(1)
.room(2).size(0.5).gain(0.2)
.slow(2)
.lpf(slider(0.475).range(200,6000))

$RandNote: n(rand.range(0,12).segment(16)).scale("g#:minor").s("wt_digital_crickets")
.orbit(2)
.room(1)
.adsr("0:.1:.1:.2")
.lpf(tri.range(100, 600).slow(2)).gain(1)

$melody:n("[0 2 4 <6 1>]/1".add(14)).scale("g#:minor").s("wt_digital_crickets")
.orbit(3)
.room(6).size(1.5).gain(0.1)
.slow(2).pan(rand)
.lpf(slider(0.411).range(200,6000)).lpenv(1)
.phaser(6).phasersweep("<800 2000 4000 8000>")

```
##Note

This week, I created a short piece using the **wt_digital_crickets** sound. I used the **add()** function to shift the instrument to different octaves and applied **orbit** to make the effects on each track sound cleaner. I also used **slider** to control the dynamics and **pan** to create a greater sense of space. I really enjoyed this assignment it was very fun and inspiring!



