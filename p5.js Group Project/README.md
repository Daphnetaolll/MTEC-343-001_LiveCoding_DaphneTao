##p5.js Group Project
For this project, I first found a moving cute shape from hydra website. And then, we start to develop it with duplicated them use ".mult". I added a noise texture blend into this small shape. At that time, KP was developing the moving path, rotation, moving speed, mouse track with ".mask(...)" at the end of the code. And I started to try to change the color of the whole visual, so I added ".blend" and insert ".solid" and ".gradient" to make the color looks beautiful. And I also added "bpm = 138" in that case we can sync the beats well. I'm really enjoy doing this cocoding assignment.

```javascript
/*	
	_hydra_only // cc teddavis.org 2022
	incase you only want to play with ~[HYDRA]LIVE
	edit hydra code within '// sandbox start/stop' for smooth (eval) changes
	cheatsheets: https://hydra.ojack.xyz/api/ + https://hydra.ojack.xyz/docs
*/

// no p5
let libs = ['https://unpkg.com/hydra-synth', 'includes/libs/hydra-synth.js']
let hydra = new Hydra()
hydra.setResolution(window.innerWidth*2, window.innerHeight*2) // retina res

bpm = 138

osc( [0.5,1].ease('linear'))
.blend(noise(10, 5),0.5)
.mask(shape(4, (0.01, ()=> 0.2 + a.fft[4]),1)
.kaleid(40)
.mult(osc(1, 1).modulate(osc(5).rotate(1.4,1),3))
.color(1,8,3)
.diff(gradient([1,0,1]))
.luma(1.2,0.05, (5, ()=> 2 + a.fft[3]))
.scale(0.6, ()=> 0.9 + a.fft[3])
.diff(o0))// o0
.modulateRepeatX(osc(1),2,({time}) => Math.sin(time) * 3)
.scroll(0.2,0.2,-0.2,-0.3)
.diff(osc(200,10,5))
.mask(
	shape([3,6].fast(0.25).ease('easeInOutCubic'),0.3,.1)
	.repeat([5,10].fast(0.125).ease('easeInOutCubic'), [5,5].fast(0.0625).ease('easeInOutCubic'))
	.scroll(  () => mouse.x / width,() => -mouse.y / height)
	.scroll(0.2,0.5,0.1,0.2)
)
.blend(
	osc(0,0,3).add(solid(0,0,1).diff(gradient(0)))
)

.out(o0)// o1
```