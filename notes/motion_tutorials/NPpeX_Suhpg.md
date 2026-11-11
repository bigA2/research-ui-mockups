# NPpeX_Suhpg
(source: transcript)

**Recipe for SAS Animation Backgrounds in After Effects:**

1. **Shape Creation:**
	* Create a new composition with a width of 1920 and a height of 1080.
	* Use the pen tool to create a star at the center of the screen.
	* Center the anchor point and change the fill color to a linear gradient.
	* Pick the colors you want (e.g., shades of blue).
	* Stretch the color key to the side for a smoother blend.
2. **Effect 1: Box Blur**
	* Add the box blur effect to the star.
	* Increase the blur radius to 50.
3. **Effect 2: Wave Warp**
	* Add the wave warp effect.
	* Change the wave type to uncircle.
	* Increase the wave height to 290.
	* Raise the wave width to 500.
	* Rotate the direction start at 135°.
	* Lower the wave speed to about 0.1.
4. **Duplicate Wave Effect:**
	* Duplicate the wave effect.
	* Change the type to sine.
	* Lower the height start at 115.
	* Rotate the direction a bit to around 280.

**Recipe for SAS Animation Backgrounds in After Effects (continued):**

1. **Background Two:**
	* Lower the visibility of the first background.
	* Create a new composition with a width of 1920 and a height of 1080.
	* Use the pen tool to draw a line in the center of the screen.
	* Set it to linear gradient and change the colors to whatever fits your style.
	* Start the color keys to the side for a smoother blend.
	* Add effects box blur effect and increase the blur radius to 150.
	* Add a wave warp.
	* Increase the height to 300 and the width to 300.
	* Change the wave type to uncircle.
	* Lower the wave speed to 0.1.
	* In rotation, rotate it to 200°.
	* In scale, un-link the values and reduce the X and Y values.
	* Add the warp effect.
	* Change the style to arch and the axis to vertical.
	* Increase the bend to 75 and lower the horizontal direction to minus 100.

**Reproducing in Remotion:**

To reproduce this in Remotion, you'll need to write code that achieves the same effects. Here's a possible implementation:

```jsx
import { interpolate, spring } from 'remotion';

// Shape creation
const shape = new Path2D();
shape.moveTo(0, 0);
shape.lineTo(100, 100);
shape.lineTo(0, 100);
shape.closePath();

// Effect 1: Box Blur
const boxBlur = spring(50, { damping: 100 });

// Effect 2: Wave Warp
const waveWarp = spring(290, { damping: 100 });
const waveWidth = spring(500, { damping: 100 });
const waveSpeed = spring(0.1, { damping: 100 });

// Duplicate Wave Effect
const duplicateWave = spring(115, { damping: 100 });
const duplicateWaveWidth = spring(500, { damping: 100 });

// Background Two
const backgroundTwo = new Path2D();
backgroundTwo.moveTo(0, 0);
backgroundTwo.lineTo(100, 100);
backgroundTwo.lineTo(0, 100);
backgroundTwo.closePath();

const boxBlurTwo = spring(150, { damping: 100 });
const waveWarpTwo = spring(300, { damping: 100 });
const waveWidthTwo = spring(300, { damping: 100 });
const waveSpeedTwo = spring(0.1, { damping: 100 });

// Animation
const animation = () => {
  const time = interpolate(0, 100, 0, 1);
  const boxBlurValue = boxBlur(time);
  const waveWarpValue = waveWarp(time);
  const waveWidthValue = waveWidth(time);
  const waveSpeedValue = waveSpeed(time);
  const duplicateWaveValue = duplicateWave(time);
  const duplicateWaveWidthValue = duplicateWaveWidth(time);
  const boxBlurTwoValue = boxBlurTwo(time);
  const waveWarpTwoValue = waveWarpTwo(time);
  const waveWidthTwoValue = waveWidthTwo(time);
  const waveSpeedTwoValue = waveSpeedTwo(time);

  // Draw the shape with the effects
  ctx.beginPath();
  ctx.moveTo(0, 0);
  ctx.lineTo(100, 100);
  ctx.lineTo(0, 100);
  ctx.closePath();
  ctx.fillStyle = `linear-gradient(${boxBlurValue}deg, ${waveWarpValue}deg, ${duplicateWaveValue}deg)`;
  ctx.fill();

  // Draw the background two
  ctx.beginPath();
  ctx.moveTo(0, 0);
  ctx.lineTo(100, 100);
  ctx.lineTo(0, 100);
  ctx.closePath();
  ctx.fillStyle = `linear-gradient(${boxBlurTwoValue}deg, ${waveWarpTwoValue}deg, ${duplicateWaveWidthValue}deg)`;
  ctx.fill();
};
```

This code uses the `remotion` library to create the same effects as the After Effects recipe.

**Recipe for the Background Animation**

1. **Background 1**
	* Color key: pink
	* Gradient taper: start length 50%
	* Anchor point: right side of the line
	* Rotation: 30 (keyframe at start), -30 (keyframe at end)
	* Turbulent displace effect: amount 24, size 300
	* Expression: time multiplied by 80
2. **Background 2**
	* Color key: red
	* Gradient taper: start length 50%
	* Anchor point: right side of the line
	* Rotation: 30 (keyframe at start), -30 (keyframe at end)
	* Turbulent displace effect: amount 24, size 300
	* Expression: time multiplied by 80
3. **Background 3**
	* Color key: orange
	* Gradient taper: start length 50%
	* Anchor point: right side of the line
	* Rotation: 30 (keyframe at start), -30 (keyframe at end)
	* Turbulent displace effect: amount 24, size 300
	* Expression: time multiplied by 80
4. **Fast Box Blur Effect**
	* Blur radius: 120
	* Scale: 50%
	* Unlink scale: yes
	* Reduce X scale: slightly
5. **Wave Warp Effect**
	* Height: 115
	* Width: 500
	* Speed: 0.1

**Recipe for the Count Percent Animation**

1. **Background**
	* Visibility: lower
	* Color key: fuchsia, orange, blue
	* Fill color: fuchsia, orange, blue
2. **Text**
	* Font: Inter bold
	* Size: 250%
	* Compress Y scale: 140
	* Counter preset effect: add
3. **Bouncing Text Effect**
	* Add to layer: yes
	* Bevel and emboss: size 7, highlight opacity 50%, shadow density 50%
	* Layer mode: overlay
4. **Solid Layer**
	* Color: black
	* Position: under background
5. **Number Layers**
	* Duplicate top number layer: yes
	* Turn off fill: yes
	* Add stroke: 8 pixels, white
	* Position: under two number layers
6. **Camera Layer**
	* Create one node camera: yes
	* Trim camera layer: yes
	* Move camera layer: forward and up

**How to Reproduce in Remotion**

To reproduce the background animation in Remotion, you can use the following code:
```jsx
import { interpolate, spring } from 'remotion';

const background1 = {
  color: 'pink',
  gradientTaper: { startLength: 0.5 },
  anchorPoint: { x: 1, y: 0 },
  rotation: spring(30, { mass: 1, damping: 20 }),
  turbulentDisplace: {
    amount: 24,
    size: 300,
  },
  expression: (time) => time * 80,
};

const background2 = {
  color: 'red',
  gradientTaper: { startLength: 0.5 },
  anchorPoint: { x: 1, y: 0 },
  rotation: spring(30, { mass: 1, damping: 20 }),
  turbulentDisplace: {
    amount: 24,
    size: 300,
  },
  expression: (time) => time * 80,
};

const background3 = {
  color: 'orange',
  gradientTaper: { startLength: 0.5 },
  anchorPoint: { x: 1, y: 0 },
  rotation: spring(30, { mass: 1, damping: 20 }),
  turbulentDisplace: {
    amount: 24,
    size: 300,
  },
  expression: (time) => time * 80,
};

const fastBoxBlur = {
  blurRadius: 120,
  scale: 0.5,
  unlinkScale: true,
  reduceXScale: true,
};

const waveWarp = {
  height: 115,
  width: 500,
  speed: 0.1,
};

// ...

export const BackgroundAnimation = () => {
  const { time } = useRemotion();

  return (
    <div>
      <Background1 {...background1} />
      <Background2 {...background2} />
      <Background3 {...background3} />
      <FastBoxBlur {...fastBoxBlur} />
      <WaveWarp {...waveWarp} />
    </div>
  );
};
```
To reproduce the count percent animation in Remotion, you can use the following code:
```jsx
import { interpolate, spring } from 'remotion';

const background = {
  color: 'fuchsia',
  fillColor: 'fuchsia',
};

const text = {
  font: 'Inter bold',
  size: 250,
  compressYScale: 140,
  counterPresetEffect: true,
};

const bouncingTextEffect = {
  add: true,
  bevel

**Recipe for the Animation**

1. **Position Keyframes**
	* Create a position keyframe at 0 seconds.
	* Move back 5 frames and create a position keyframe.
	* Move back 5 frames and create a position keyframe.
	* Shift the camera slightly to the right and create a position keyframe.
	* Move the keyframe to the start of the layer.
	* Move the keyframe to the end of the layer.
2. **Trim Layer**
	* Create a position keyframe at 1.5 seconds.
	* Move back 5 frames and create a position keyframe.
	* Move back 5 frames and create a position keyframe.
	* Shift the camera slightly to the right and create a position keyframe.
	* Move the keyframe to the start of the second camera layer.
3. **Graph Editor**
	* Select the keyframes and open the graph editor.
	* Combine both graphs into one smooth motion curve.
4. **Adjustment Layer**
	* Create an adjustment layer.
	* Add the fast box blur effect to the adjustment layer.
	* Increase the blur radius to 30 and create a keyframe.
	* Move back 5 frames and reset it to zero.
5. **Number Layers**
	* Create opacity keyframes for the number layers.
	* Move forward slightly and set the opacity to 0%.
	* Trim the layers after the keyframe.
6. **Background Layer**
	* Turn on the background layer and change the blue to a light yellow.
7. **Rectangle Layers**
	* Select all the rectangle layers and move them to second three.
	* Turn all the layers into 3D and create position keyframes.
	* Move the keyframes to the start of the layer and forward until they disappear.
	* Open the graph editor and create a fast ease in.
8. **Video Layers**
	* Add the four videos to the comp and scale them down to 40%.
	* Duplicate the videos three times and add them to the point where the video starts.
	* Move backward to the same point, then trim and delete the extra part.
9. **Linking Layers**
	* Link each video layer with the corresponding rectangle layer using track mate and parent.
10. **3D Layers**
	* Turn all the video layers into 3D so they can move with the rectangles.
11. **Glass-Like Layer**
	* Duplicate the layer, move the duplicated under the original layer, and turn its visibility back on.
	* Increase the size of the duplicated layer.
	* Turn the layer into an adjustment layer and add the fast box blur effect.
	* Increase the blur radius to five and add a transform effect.
	* Increase the scale to 120.

**Reproducing the Animation in Remotion**

To reproduce the animation in Remotion, you can use the following code:

```jsx
import { spring } from 'remotion';

const animation = () => {
  const position = spring(0, {
    fps: 60,
    mass: 20,
    tension: 300,
    friction: 40,
  });

  const trimLayer = spring(1.5, {
    fps: 60,
    mass: 20,
    tension: 300,
    friction: 40,
  });

  const graphEditor = spring(0, {
    fps: 60,
    mass: 20,
    tension: 300,
    friction: 40,
  });

  const adjustmentLayer = spring(30, {
    fps: 60,
    mass: 20,
    tension: 300,
    friction: 40,
  });

  const numberLayers = spring(0, {
    fps: 60,
    mass: 20,
    tension: 300,
    friction: 40,
  });

  const backgroundLayer = spring(0, {
    fps: 60,
    mass: 20,
    tension: 300,
    friction: 40,
  });

  const rectangleLayers = spring(0, {
    fps: 60,
    mass: 20,
    tension: 300,
    friction: 40,
  });

  const videoLayers = spring(0, {
    fps: 60,
    mass: 20,
    tension: 300,
    friction: 40,
  });

  return (
    <div>
      <div style={{ position: 'absolute', top: position, left: position }}>
        {/* animation content */}
      </div>
      <div style={{ position: 'absolute', top: trimLayer, left: trimLayer }}>
        {/* trim layer content */}
      </div>
      <div style={{ position: 'absolute', top: graphEditor, left: graphEditor }}>
        {/* graph editor content */}
      </div>
      <div style={{ position: 'absolute', top: adjustmentLayer, left: adjustmentLayer }}>
        {/* adjustment layer content */}
      </div>
      <div style={{ position: 'absolute', top: numberLayers, left: numberLayers }}>
        {/* number layers content */}
      </div>
      <div style={{ position: 'absolute', top: backgroundLayer, left: backgroundLayer }}>
        {/* background layer content */}
      </div>
      <div style={{ position: 'absolute',

**Recipe for the After Effects Animation:**

1. **Glass Layer:**
	* Create a new composition and add a glass layer.
	* Name it "color of transformation".
	* Trim and delete the part of the layer before the delete point.
	* Move slightly forward to see the glass layer.
	* Turn all the layers into 3D.
	* Create an offset of three frames between each layer.
	* Move the glass layer slightly backward.
2. **Adjustment Layer:**
	* Add a new adjustment layer.
	* Position it so it starts exactly with the first rectangle appearance.
	* Add a fast box blur effect with a radius of 5.
	* Add a chromatic aberration effect with an aberration of 50.
3. **Circle Mask:**
	* Create a circle mask in the center of the screen on the adjustment layer.
	* Invert the mask and increase the mask feather to 330.
	* Stretch the mask slightly to the sides.
4. **Rectangle Animation:**
	* Create a new composition and add a white rectangle at the bottom of the screen.
	* Increase the roundness to 500 and center the anchor point.
	* Create position and scale keyframes.
	* Move forward 20 frames and increase the scale to 230%.
	* Move the rectangle up to the center and shift it slightly to the right.
	* Create another scale keyframe and move 1 second forward.
	* Copy and paste the first keyframes and reduce the scale to 90%.
	* Open the graph editor and create a fast easing.
5. **Glass Reflection Effect:**
	* Turn the rectangle into an adjustment layer.
	* Add a fast box blur effect with a radius of 100.
	* Add a transform and set the scale to 160.
	* Duplicate the layer and turn off the adjustment.
	* Delete its effects and add a 1-pixel white stroke.
6. **Arrow Icon:**
	* Add the arrow icon layer and place it in the center of the circle.
	* Link it to the search bar base rectangle.
	* Create a position keyframe and move five frames forward.
	* Lower the arrow slightly and move five frames forward.
	* Raise the arrow outside the circle.
	* Trim the layer and delete its keyframes.
7. **Circle Animation:**
	* Create a new keyframe and move seven frames forward.
	* Raise the arrow back to the center of the circle.
	* Select the keyframes and add a position bounce.
8. **Color Effect:**
	* Duplicate the circle layer and move it above.
	* Turn off the adjustment and delete its effects.
	* Select the two arrow layers and use the track mat to confine them within the circle.
	* Duplicate the top circle layer and move the duplicate under.
	* Turn its visibility back on.
	* Add a four-color gradient and position each color point at the edge of the circle.
	* Change the first color to black, the second to dark blue, and the last two to black.
	* Select point two and position it at the start of the circle.
	* Move slightly back to 2 seconds and 5 frames.
	* Trim and delete the part before.
	* Create a point two keyframe and move 10 frames forward.
	* Raise the point and trim and delete after.
	* Lower the opacity to 0% and create a keyframe.
	* Move slightly back and store it to 100%.
	* Move slightly after to the start.
	* Create another keyframe and go to the start of the layer.
	* Lower it to 0%.
	* Change the layer mode to screen.

**Reproducing the Animation in Remotion:**

To reproduce the animation in Remotion, you can use the following code:

```jsx
import { interpolate, spring } from 'remotion';

const glassLayer = {
  x: 0,
  y: 0,
  scale: 1,
  rotation: 0,
  opacity: 1,
};

const adjustmentLayer = {
  x: 0,
  y: 0,
  scale: 1,
  rotation: 0,
  opacity: 1,
};

const rectangleLayer = {
  x: 0,
  y: 0,
  scale: 1,
  rotation: 0,
  opacity: 1,
};

const arrowLayer = {
  x: 0,
  y: 0,
  scale: 1,
  rotation: 0,
  opacity: 1,
};

const circleLayer = {
  x: 0,
  y: 0,
  scale: 1,
  rotation: 0,
  opacity: 1,
};

const animation = () => {
  const time = useCurrentTime();

  // Glass Layer
  const glassX = interpolate(time, [0, 20], [0, 100]);
  const glassY = interpolate(time, [0, 20], [0, 100]);
  const glassScale = interpolate(time, [0, 20], [1, 2]);
  const glassRotation = interpolate(time, [0, 20], [0, 360]);
  const glassOpacity = interpolate(time, [0,
