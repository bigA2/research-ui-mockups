# iRkEN4doyeQ
(source: transcript)

**Recipe for the After Effects Composition:**

1. **Composition Settings:**
	* Name: placeholder
	* Resolution: 180x350 pixels
	* Frame Rate: 30 frames per second
	* Duration: 20 seconds
2. **Rectangle Tool:**
	* Create a shape with the rectangle tool
	* Rename it
	* Center the anchor point and center it in the viewport
	* Disable the chain
	* Set the dimensions to 180x350 pixels
	* Round the corners to 100 pixels
	* Change the fill to gradient fill
	* Position the gradient handles
3. **Gradient:**
	* Add a new color to the gradient
	* Use the eyropper tool to select the colors
	* Duplicate the layer and rename it to stroke
	* Remove the gradient from the stroke layer and add a gradient stroke
	* Position the stroke handles
4. **Text Tool:**
	* Create a box with the text tool
	* Type the paragraph
	* Press the control key to snap the text to the center of the shape
	* Parent the text to the shape
	* Use the font Cool Vetica in its light version
	* Set the parameters for the text layer
5. **Ellipse Tool:**
	* Create an ellipse with the same gradient
	* Duplicate the layer and rename it to stroke
	* Remove the gradient and add a stroke
	* Position the stroke handles
	* Parent the stroke to the ellipse
6. **Icon:**
	* Add an icon from the project files assets
	* Center it and adjust its scale
	* Apply a fill effect with the same color as the stroke
	* Make this layer a guide layer
7. **Glow Effect:**
	* Add a little glow to the stroke using the deep glow plugin
	* Lower the radius and intensity a bit
	* If you don't have the plugin installed, use the glow effect and increase the radius slightly

**Reproducing the Composition in Remotion:**

To reproduce the composition in Remotion, you would need to write code to achieve the same effects. Here's a possible implementation:

```jsx
import { useSpring, a } from '@react-spring/web';
import { useFrame } from '@react-three/fiber';

const Rectangle = () => {
  const [rect, api] = useSpring(() => ({
    width: 180,
    height: 350,
    cornerRadius: 100,
    fill: 'linear-gradient(to bottom, #f7f7f7, #f7f7f7)',
  }));

  useFrame(() => {
    api.update({
      width: 180,
      height: 350,
      cornerRadius: 100,
      fill: 'linear-gradient(to bottom, #f7f7f7, #f7f7f7)',
    });
  });

  return (
    <a.group ref={ref => api.set(ref)}>
      <a.mesh ref={ref => api.set(ref)}>
        <a.planeGeometry args={[rect.width, rect.height]} />
        <a.meshBasicMaterial
          ref={ref => api.set(ref)}
          color="#f7f7f7"
          opacity={1}
          transparent={true}
        />
      </a.mesh>
    </a.group>
  );
};

const Text = () => {
  const [text, api] = useSpring(() => ({
    fontSize: 24,
    fontFamily: 'Cool Vetica',
    color: '#333',
  }));

  useFrame(() => {
    api.update({
      fontSize: 24,
      fontFamily: 'Cool Vetica',
      color: '#333',
    });
  });

  return (
    <a.group ref={ref => api.set(ref)}>
      <a.mesh ref={ref => api.set(ref)}>
        <a.textGeometry args={['Hello World', text]} />
        <a.meshBasicMaterial
          ref={ref => api.set(ref)}
          color="#333"
          opacity={1}
          transparent={true}
        />
      </a.mesh>
    </a.group>
  );
};

const Ellipse = () => {
  const [ellipse, api] = useSpring(() => ({
    width: 180,
    height: 350,
    cornerRadius: 100,
    fill: 'linear-gradient(to bottom, #f7f7f7, #f7f7f7)',
  }));

  useFrame(() => {
    api.update({
      width: 180,
      height: 350,
      cornerRadius: 100,
      fill: 'linear-gradient(to bottom, #f7f7f7, #f7f7f7)',
    });
  });

  return (
    <a.group ref={ref => api.set(ref)}>
      <a.mesh ref={ref => api.set(ref)}>
        <a.planeGeometry args={[ellipse.width, ellipse.height]} />
        <a.meshBasicMaterial
          ref={ref => api.set(ref)}
          color="#f7f7f7"
          opacity={1}
          transparent={true}
        />
      </a.mesh>
    </a.group>
  );
};

const Icon = () => {
  const [icon, api] = useSpring(() => ({

**Recipe for the After Effects SaaS Tutorial**

**Step 1: Create a Hexagon Composition**

1. Duplicate the composition 6 times.
2. Set the anchor point to the center of each composition.
3. Set the rotation to:
	* -120° for the first composition
	* -240° for the second composition
	* -360° for the third composition
	* -480° for the fourth composition
	* -600° for the fifth composition
	* -720° for the sixth composition
4. Press Ctrl + Alt + Home to center the anchor point.

**Step 2: Create a Null Object**

1. Create a new null object.
2. Convert the null object to 3D.
3. Place the null object in the center of the compositions.
4. Parent all the compositions to the null object.

**Step 3: Animate the Rotation**

1. Set a keyframe for X and Y rotation at the 6-second mark.
2. Set the Y rotation to 360° and the X rotation to 25°.
3. Smooth the keyframes and set the influence on the handles to around 70%.

**Step 4: Animate the Curvature**

1. Change the render engine to Advanced 3D.
2. Set the number of segments to 20.
3. Set the curvature to zero.
4. Add an ambient light with an intensity of 100.
5. Go to the beginning of the timeline and set a keyframe for curvature.
6. Move 25 frames forward and set the curvature to -40.
7. Smooth all the keyframes and move the handles to the left.

**Step 5: Add a Small Rotation Animation**

1. Mark a keyframe on the Y axis.
2. Move 25 frames forward and place the keyframes there.
3. Smooth the keyframes and give the curve the same shape.

**Step 6: Lower the Opacity**

1. Lower the opacity of the compositions to 98%.

**Step 7: Duplicate Compositions**

1. Duplicate the compositions 5 times.
2. Replace the duplicate compositions with new ones.

**Step 8: Animate the Star**

1. Create a new shape layer and add a poly star with 4 points.
2. Set the inner radius to 30 and the outer radius to 80.
3. Set the inner roundness to 200%.
4. Convert the star to 3D and make sure the classic 3D render engine is activated.
5. Set a keyframe for position and Z rotation at the beginning of the timeline.
6. Move the star forward on the Z axis until it fills the entire composition.
7. Set the Z-axis value to -2595 and the rotation to -45°.
8. Move forward to 110 and continue animating the Z-axis.
9. Set the rotation to 90° and the Z-axis value to -2140.
10. Smooth all the keyframes and move the handles to the left.

**Step 9: Add a Curve to the Trajectory**

1. Select the convert vertex tool and position the handles roughly.
2. Smooth all the keyframes and move the handles to the left.

**Reproducing the Animation in Remotion**

To reproduce the animation in Remotion, you can use the following code:

```jsx
import { spring } from 'remotion';

const animation = () => {
  const x = spring(0, { fps: 60 });
  const y = spring(0, { fps: 60 });
  const z = spring(0, { fps: 60 });

  const star = {
    x: x.interpolate({
      inputRange: [0, 110],
      outputRange: [-2595, -2140],
    }),
    y: y.interpolate({
      inputRange: [0, 110],
      outputRange: [-45, 90],
    }),
    z: z.interpolate({
      inputRange: [0, 110],
      outputRange: [0, 0],
    }),
  };

  return (
    <div>
      <div
        style={{
          position: 'absolute',
          top: 0,
          left: 0,
          width: '100%',
          height: '100%',
          backgroundColor: 'white',
          borderRadius: 30,
          transform: `translate3d(${star.x}px, ${star.y}px, ${star.z}px)`,
        }}
      />
    </div>
  );
};
```

This code uses the `spring` function from Remotion to animate the position of the star. The `interpolate` function is used to create a smooth animation curve. The `inputRange` and `outputRange` properties are used to define the animation curve. The `fps` property is used to set the frame rate of the animation.

**Recipe for the After Effects Animation:**

1. **Star Movement:**
	* Set keyframes for position handles at 70%, 50%, and 90% influence.
	* Modify entry and exit speeds by double-clicking on keyframes and activating the continuous option.
	* Move handles up to create a smooth animation.
	* Set rotation values to 500 and adjust rotation curve handles to 100%, 50%, and 90%.
2. **Background Animation:**
	* Create a solid layer and apply a four-color gradient effect.
	* Use the Eyedropper tool to color the background.
	* Create a shape with the Pen tool and apply a Fast Box Blur effect.
	* Adjust the blur amount to 150 and experiment with blending modes.
3. **Particles Animation:**
	* Adjust the scale and alpha mat of particles to match the light beam.
	* Change the blending mode of particles to Screen.
	* Lower the opacity of particles to create a subtle effect.
4. **Transition between Scenes:**
	* Duplicate the star composition and add a small animation to the opacity.
	* Mark keyframes for opacity at 0, 100, and 0.
	* Smooth the keyframes with F9.
5. **3D Animation:**
	* Convert the star composition to 3D.
	* Create a 35mm camera with one node and parent it to a null object.
	* Add a solid layer as the background for the second scene.
	* Apply a gradient ramp effect and cut the layer at the transition point.
6. **Text Animation:**
	* Convert the text to 3D and center its anchor point.
	* Add a small animation to the text by moving it down and setting the opacity to 0.
	* Use the Range Selector to offset the keyframes and set the ease high to 20 and the ease low to 100.

**Reproducing the Animation in Remotion:**

To reproduce the animation in Remotion, you'll need to write code that achieves the same effects. Here's a rough outline of the steps:

1. **Star Movement:**
	* Use the `interpolate` function to create a smooth animation for the star's position.
	* Use the `spring` function to create a smooth animation for the star's rotation.
	* Set the `influence` property to 70%, 50%, and 90% to match the After Effects animation.
2. **Background Animation:**
	* Use the `createSolid` function to create a solid layer and apply a four-color gradient effect.
	* Use the `Eyedropper` function to color the background.
	* Create a shape with the `Pen` function and apply a Fast Box Blur effect.
	* Adjust the blur amount and experiment with blending modes.
3. **Particles Animation:**
	* Use the `adjustScale` function to adjust the scale of particles.
	* Use the `alphaMat` function to adjust the alpha mat of particles.
	* Change the blending mode of particles to Screen.
	* Lower the opacity of particles to create a subtle effect.
4. **Transition between Scenes:**
	* Duplicate the star composition and add a small animation to the opacity.
	* Use the `interpolate` function to create a smooth animation for the opacity.
	* Mark keyframes for opacity at 0, 100, and 0.
	* Smooth the keyframes with a function like `easeInOut`.
5. **3D Animation:**
	* Convert the star composition to 3D using the `convertTo3D` function.
	* Create a 35mm camera with one node and parent it to a null object.
	* Add a solid layer as the background for the second scene.
	* Apply a gradient ramp effect and cut the layer at the transition point.
6. **Text Animation:**
	* Convert the text to 3D using the `convertTo3D` function.
	* Add a small animation to the text by moving it down and setting the opacity to 0.
	* Use the `RangeSelector` function to offset the keyframes and set the ease high to 20 and the ease low to 100.

Here's some sample code to get you started:
```jsx
import { createSolid, Eyedropper, Pen, interpolate, spring } from 'remotion';

const star = createSolid({
  width: 100,
  height: 100,
  backgroundColor: 'white',
});

const background = createSolid({
  width: 1920,
  height: 1080,
  backgroundColor: 'black',
});

const particles = createSolid({
  width: 100,
  height: 100,
  backgroundColor: 'white',
});

const text = createSolid({
  width: 100,
  height: 100,
  backgroundColor: 'white',
});

const animation = () => {
  const t = interpolate(0, 1, 0, 100);

  return (
    <div>
      <star
        style={{
          position: 'absolute',
          top: 0,
          left: 0,
          width: 100,
          height: 100,
          backgroundColor: 'white',
          transform: `translate(${t}%, 0%)`,
        }}

**Recipe for the Animation**

1. **Grid Layer**
	* Set layer to overlay mode
	* Grid thickness: 2
	* Move grid backward on Z-axis: 1000 pixels
	* Scale animation:
		+ Keyframe 1: 0s (no scale)
		+ Keyframe 2: 11:10s (scale to 50%)
		+ Ease: Smooth (F9)
2. **Camera Layer**
	* Move camera backward: -300 pixels
	* Keyframe 1: 0s (no movement)
	* Keyframe 2: 11:10s (move camera backward)
	* Ease: Smooth (F9)
3. **Shine Layer**
	* Create solid with blue color
	* Apply fastbox blur effect: 100
	* Set layer to screen mode
	* Place layer below star composition
	* Mask shape: use pen tool to create shape
	* Apply fastbox blur effect: 100
	* Set layer to screen mode
	* Convert layer to 3D: scale to fill composition
	* Cut layer at 11:10s
	* Add animation to mask expansion:
		+ Keyframe 1: 0s (no expansion)
		+ Keyframe 2: 325s (expand mask)
		+ Ease: Smooth (F9)
4. **Ellipse Layer**
	* Create ellipse with shift key
	* Rename layer
	* Convert to 3D: center anchor point
	* Set layer to same depth as shine layer
	* Clip layer
	* Change fill to radial gradient
	* Position gradient handles
	* Move ellipse down on Y-axis: 10 pixels
	* Add animation to ellipse position:
		+ Keyframe 1: 0s (no movement)
		+ Keyframe 2: 325s (move ellipse down)
		+ Ease: Smooth (F9)
5. **Stroke Layer**
	* Duplicate ellipse layer
	* Remove fill: leave only stroke
	* Set stroke thickness: 40 pixels
	* Add blur to stroke: 30
	* Add layer to composition
	* Duplicate stroke layer: reduce thickness and blur
	* Place duplicate layers down
	* Move layers slightly to the right
6. **Particle Layer**
	* Duplicate particle layer
	* Disable matte alpha
	* Remove opacity keyframes
	* Set Z-axis rotation: -90°
	* Increase scale
	* Make layer matte alpha of shine layer
	* Make layer visible
7. **Adjustment Layer**
	* Create adjustment layer
	* Apply curves effect: add contrast
	* Tweak blue channel: add slight contrast
	* Lighten gradient on shape: 10%

**Reproducing the Animation in Remotion**

To reproduce the animation in Remotion, you can use the following code:
```jsx
import { useSpring, animated } from '@remotion/react-spring';

const springConfig = {
  stiffness: 100,
  damping: 20,
};

const gridLayer = () => {
  const { x, y } = useSpring({
    x: 0,
    y: 0,
    config: springConfig,
  });

  return (
    <animated.div
      style={{
        position: 'absolute',
        top: y,
        left: x,
        width: 100,
        height: 100,
        backgroundColor: 'gray',
        opacity: 0.5,
      }}
    />
  );
};

const cameraLayer = () => {
  const { x, y } = useSpring({
    x: 0,
    y: 0,
    config: springConfig,
  });

  return (
    <animated.div
      style={{
        position: 'absolute',
        top: y,
        left: x,
        width: 100,
        height: 100,
        backgroundColor: 'blue',
        opacity: 0.5,
      }}
    />
  );
};

const shineLayer = () => {
  const { x, y } = useSpring({
    x: 0,
    y: 0,
    config: springConfig,
  });

  return (
    <animated.div
      style={{
        position: 'absolute',
        top: y,
        left: x,
        width: 100,
        height: 100,
        backgroundColor: 'yellow',
        opacity: 0.5,
      }}
    />
  );
};

const ellipseLayer = () => {
  const { x, y } = useSpring({
    x: 0,
    y: 0,
    config: springConfig,
  });

  return (
    <animated.div
      style={{
        position: 'absolute',
        top: y,
        left: x,
        width: 100,
        height: 100,
        borderRadius: '50%',
        backgroundColor: 'red',
        opacity: 0.5,
      }}
    />
  );
};

const strokeLayer = () => {
  const { x, y } = useSpring({
    x: 0,
    y: 0,
    config: springConfig,
  });

  return (
    <animated.div
      style={{
