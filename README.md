# forge-pinch-zoom
customized iPad/IPhone/Android pinch zoom touch controls for ForgeViewer

Found a much more pleasing way...
On touchend event, set the pivot to the center of the canvas.
This is simple and very intuitive for navigation.

Try the demo on your iPad or Android Tablet here:

DEMO: 


### Goal:

- Pinch zoom sets zoom point to pivot. 
- Rotation is always turntable style. 
- When panning with two fingers the model must not be rotated.


### Resources:

Steps:
- https://www.keanw.com/2017/04/fixing-pinch-zoom-in-forge-viewer-applications.html
- https://forge.autodesk.com/blog/lock-rotation-around-z-viewer
 
 
And this…
 
viewer.navigation.setPivotPoint({x: -0.7180065711871748, y: -11.258963707247002, z: 0})
 
 
Need to do a `RAYHIT` on mouse up (touch event) to the center of the screen.  Get the result x,y,z , if something 'hit', set  pivot to that x,y,z.

If no hit on mouse up, do not update pivot point.
