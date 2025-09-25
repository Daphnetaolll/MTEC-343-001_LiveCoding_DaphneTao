## Percussion Patch

```Javascript

setcpm(140/4)
$: s("bd ~ bd ~ ")
.bank("yamahary30")
.room (.05)

$: s("~ sd ~ sd")
.bank ("rolandtr505")
.room (.1).gain(1)

$: s("~ hh*2 ~ hh*2 ~ hh*2 ~ hh*2")
.bank("rolandtr808")
.room(.1).gain(2)

$: s("[hh!16? | hh!6 ~ ~!6 | ~ ~!6 hh!3 | ~ ~ ~ hh!12 ]")
.bank("lm2")
.hpf(3000).lpf(4000).room (.1).roomsize(4)

$: s("~ ~ ~ cp?")
.bank("rm50") 
.room(.15).roomsize(10)
