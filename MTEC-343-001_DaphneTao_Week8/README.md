##Oct 23 Blue Reflections
By Daphne Tao

####For this assignment, I started by exploring Hydra and found a patch that I really liked because of its smooth, silk like texture. I began by modifying the color palette to create a softer and more dreamlike tone. Then, I adjusted the zoom level, as well as the speed and direction of the wave motion, to enhance the sense of depth and fluidity.

####Finally, I wanted to add a visual element that looked like butterflies gliding over water. To achieve this, I incorporated a rotating hexagonal pattern as a reflection layer on top of the original texture. The result feels dynamic and elegant, combining organic motion with geometric balance.

```javascript
noise()
.color(() => a.fft[2]*2,0,.6)
.modulate(noise(() => a.fft[0]*10))
.scale(()=> a.fft[2]*5)
.layer(
  src(o0)
  .mask(osc(1).modulateRotate(osc(),90,0))
  .scale(() => a.fft[0]*2)
  .luma(0.2,0.3)
)
.blend(o0)
.out(o0)

osc()
.modulate(noise(() => a.fft[1]+5))
.color(0.1,0.7,2)
.out(o1)

src(o0)
.modulate(o1)
.layer(
  src(o1)
  .mask(o1)
  .saturate(3)
)
.modulateRotate(o1)
.rotate(({time}) => time%360*0.05)
.out(o2)
render(o2)


shape(7).scale(0.8,0.7,0.2).repeatX(3.0, 4.0).repeatY(2.0, 4.0).scrollX([-1,1].smooth()).rotate([-2,1].ease('easeInOutCubic')).out(o0)



```
[Link]
(https://hydra.ojack.xyz/?code=JTJGJTJGJTIwbGljZW5zZWQlMjB3aXRoJTIwQ0MlMjBCWS1OQy1TQSUyMDQuMCUyMGh0dHBzJTNBJTJGJTJGY3JlYXRpdmVjb21tb25zLm9yZyUyRmxpY2Vuc2VzJTJGYnktbmMtc2ElMkY0LjAlMkYlMEElMkYlMkYlMjBWZWx2ZXQlMjBQb29sJTBBJTJGJTJGJTIwYnklMjBNYWhhbGlhJTIwSC1SJTBBJTJGJTJGJTIwSUclM0ElMjBtbV9ocl8lMEElMEElMEFub2lzZSgpJTBBLmNvbG9yKCgpJTIwJTNEJTNFJTIwYS5mZnQlNUIyJTVEKjIlMkMwJTJDLjYpJTBBLm1vZHVsYXRlKG5vaXNlKCgpJTIwJTNEJTNFJTIwYS5mZnQlNUIwJTVEKjEwKSklMEEuc2NhbGUoKCklM0QlM0UlMjBhLmZmdCU1QjIlNUQqNSklMEEubGF5ZXIoJTBBJTIwJTIwc3JjKG8wKSUwQSUyMCUyMC5tYXNrKG9zYygxKS5tb2R1bGF0ZVJvdGF0ZShvc2MoKSUyQzkwJTJDMCkpJTBBJTIwJTIwLnNjYWxlKCgpJTIwJTNEJTNFJTIwYS5mZnQlNUIwJTVEKjIpJTBBJTIwJTIwLmx1bWEoMC4yJTJDMC4zKSUwQSklMEEuYmxlbmQobzApJTBBLm91dChvMCklMEElMEFvc2MoKSUwQS5tb2R1bGF0ZShub2lzZSgoKSUyMCUzRCUzRSUyMGEuZmZ0JTVCMSU1RCUyQjUpKSUwQS5jb2xvcigwLjElMkMwLjclMkMyKSUwQS5vdXQobzEpJTBBJTBBc3JjKG8wKSUwQS5tb2R1bGF0ZShvMSklMEEubGF5ZXIoJTBBJTIwJTIwc3JjKG8xKSUwQSUyMCUyMC5tYXNrKG8xKSUwQSUyMCUyMC5zYXR1cmF0ZSgzKSUwQSklMEEubW9kdWxhdGVSb3RhdGUobzEpJTBBLnJvdGF0ZSgoJTdCdGltZSU3RCklMjAlM0QlM0UlMjB0aW1lJTI1MzYwKjAuMDUpJTBBLm91dChvMiklMEFyZW5kZXIobzIpJTBBJTBBJTBBc2hhcGUoNykuc2NhbGUoMC44JTJDMC43JTJDMC4yKS5yZXBlYXRYKDMuMCUyQyUyMDQuMCkucmVwZWF0WSgyLjAlMkMlMjA0LjApLnNjcm9sbFgoJTVCLTElMkMxJTVELnNtb290aCgpKS5yb3RhdGUoJTVCLTIlMkMxJTVELmVhc2UoJ2Vhc2VJbk91dEN1YmljJykpLm91dChvMCklMEElMEElMEE%3D)
