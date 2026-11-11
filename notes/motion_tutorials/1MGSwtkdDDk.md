# 1MGSwtkdDDk
(source: transcript)

**Recipe for the Text Animation in After Effects:**

1. **Composition Settings:**
	* Resolution: 4K
	* Frame Rate: 25 frames per second
	* Duration: Not specified
2. **Background:**
	* Create an ellipse shape
	* Drag it out to create a circle
	* Center it in the composition
	* Add a layer style: Outer Glow
		+ Color Type: Gradient
		+ Opacity: 85%
		+ Size: Increased to see the glow
	* Edit the gradient to add a light blue, darker blue, and black
	* Add a tiny bit of noise (10%)
	* Increase the range of the noise
3. **Background Animation:**
	* Set a keyframe for the scale at 0%
	* Go to the graph editor and drag the last keyframe to the left
	* Duplicate the background and scale it up
	* Duplicate the background again and scale it up
4. **Mask:**
	* Create a new solid layer
	* Use the rectangle tool to create a mask
	* Feather the mask by a lot
	* Set the transparency to a low value
5. **Text Animation:**
	* Create a new text layer
	* Type the text: "animation"
	* Use the font: San Francisco Pro
	* Center the text
	* Animate the position using the range selector
		+ Based on: Words
		+ Shape: Ramp up
		+ Ease: Low to 100%
	* Set a keyframe for the offset at 100%
	* Drag the keyframe to the left and set it to -100%
	* Change the position value to a lower value
6. **Opacity Animation:**
	* Add the property: Opacity
	* Set the opacity to 0%
7. **Color Animation:**
	* Add the property: Fill Color RGB
	* Set the color to a lighter blue to match the background
8. **Motion Blur:**
	* Turn on motion blur

**Reproducing the Animation in Remotion:**

To reproduce the animation in Remotion, you would need to write code to achieve the same effects. Here's a possible implementation:

```jsx
import { spring } from 'remotion';
import { interpolate } from 'remotion';

const background = () => {
  const scale = spring(1, { damping: 100 });
  return (
    <group>
      <ellipse
        cx={0}
        cy={0}
        rx={100}
        ry={100}
        fill="#fff"
        stroke="#000"
        strokeWidth={2}
      />
      <ellipse
        cx={0}
        cy={0}
        rx={100}
        ry={100}
        fill="#fff"
        stroke="#000"
        strokeWidth={2}
        style={{
          transform: `scale(${scale})`,
        }}
      />
      <ellipse
        cx={0}
        cy={0}
        rx={100}
        ry={100}
        fill="#fff"
        stroke="#000"
        strokeWidth={2}
        style={{
          transform: `scale(${scale})`,
        }}
      />
    </group>
  );
};

const text = () => {
  const opacity = spring(1, { damping: 100 });
  const color = interpolate(0, 1, '#000', '#fff');
  return (
    <group>
      <text
        x={0}
        y={0}
        text="animation"
        fill={color}
        opacity={opacity}
        fontSize={24}
        fontFamily="San Francisco Pro"
      />
    </group>
  );
};

const mask = () => {
  const opacity = spring(1, { damping: 100 });
  return (
    <group>
      <rect
        x={0}
        y={0}
        width={100}
        height={100}
        fill="#fff"
        opacity={opacity}
      />
    </group>
  );
};

const animation = () => {
  return (
    <group>
      {background()}
      {text()}
      {mask()}
    </group>
  );
};

export default animation;
```

This code uses the `spring` function from Remotion to animate the scale of the background, the opacity of the text, and the opacity of the mask. It also uses the `interpolate` function to animate the color of the text. The animation is then exported as a Remotion component.

**Recipe:**

1. **Duplicate Animator**
	* Duplicate the animator by pressing Command + D (Mac) or Control + D (Windows)
2. **Split Animator**
	* Go into the duplicated animator and delete the opacity and fill color by selecting them and hitting backspace
	* Delete the position in the other animator
3. **Add Selector Expression**
	* Select the animator with the position and add a selector expression
	* Open the expression and paste the code
4. **Change Keyframe Timing**
	* Press U to see the keyframes and make the keyframe quicker
	* Open the expression and paste a different code to change the animation to be based on words
5. **Change Background**
	* Create a new background by duplicating the composition and making it white
	* Add a new solid layer and adjust the color to a light white
6. **Create Blobs**
	* Create a new ellipse and make it blue
	* Duplicate the ellipse and make the fill color darker
	* Add a wiggle path to the ellipse and adjust the points to smooth and detail to one
	* Move the wiggle path outside of the ellipse to affect all the blobs
7. **Add Blur**
	* Add a Gaussian blur or fast box blur to the blobs
	* Set the repeat edge pixels to off and the blur to a high value (e.g. 400 or 800)

**Settings:**

1. **Keyframe Timing:**
	* Frame 0: 0%
	* Frame 10: 100%
	* Easing: Ease In
2. **Selector Expression:**
	* Code: `thisLayer.property("Position").valueAtTime(time)`
3. **Wiggle Path:**
	* Points: Smooth
	* Detail: 1
	* Size: High
	* Per Second: 1
4. **Blur:**
	* Type: Gaussian Blur or Fast Box Blur
	* Repeat Edge Pixels: Off
	* Blur: High value (e.g. 400 or 800)

**Remotion Code:**

To reproduce this animation in Remotion, you can use the following code:
```jsx
import { spring } from 'remotion';

const animation = spring({
  from: 0,
  to: 1,
  duration: 10,
  easing: 'easeIn',
});

const wigglePath = {
  points: 'smooth',
  detail: 1,
  size: 10,
  perSecond: 1,
};

const blur = {
  type: 'GaussianBlur',
  repeatEdgePixels: false,
  blur: 400,
};

const blobs = [
  {
    fill: 'blue',
    wigglePath,
  },
  {
    fill: 'darker blue',
    wigglePath,
  },
];

const animation = (
  <div>
    {blobs.map((blob, index) => (
      <div key={index} style={{ position: 'absolute', top: 0, left: 0 }}>
        <div
          style={{
            width: 100,
            height: 100,
            backgroundColor: blob.fill,
            borderRadius: 50,
            transform: `translate(${animation(index * 10)})`,
            filter: `blur(${blur.blur}px)`,
          }}
        />
      </div>
    ))}
  </div>
);
```
Note that this code is a simplified version of the original animation and may not exactly match the settings and behavior of the original animation.

**Recipe for the Motion Design**

**1. Text Animation**

- Set the text to dark, almost fully black, with a hint of blue.
- Center the text by holding Command (or Control on Windows) and clicking.
- Add the typewriter preset and double-click on it.
- Select all keyframes and hit F9 to go to the graph editor.
- Easy ease the keyframes to make the animation smooth.

**2. Blinking Cursor**

- Use the pen tool to draw a quick line for the blinking cursor.
- Make sure the stroke is a bit thicker and customize it as needed.
- Set a keyframe for the position of the cursor and easy ease it.
- Align the cursor with the text and make sure it's in front of it.
- If desired, manually keyframe the transparency to create a blinking effect.

**3. Animation Presets**

- Select the animator and drag it to the animation presets.
- Save the animation as a preset, such as "SAS animator".
- Name the preset and save it for future use.

**4. Background Animation**

- Add a background animation by creating a new layer.
- Use the noise effect to create a subtle texture.
- Adjust the noise settings to achieve the desired effect.
- Add a tritone to the background to create a gradient effect.

**5. UI Mockup Handling**

- Use the fast box blur effect to create a blurred background.
- Turn off the fast box blur effect to see the colors of the background.
- Adjust the colors of the background to achieve the desired effect.

**6. Typography Sizes/Fonts**

- Use a dark, almost fully black font with a hint of blue.
- Adjust the font size and style to achieve the desired effect.

**7. Sound**

- Add a sound effect to the animation to enhance the user experience.
- Adjust the sound settings to achieve the desired effect.

**Reproducing the Animation in Remotion**

To reproduce the animation in Remotion, you can use the following code:

```jsx
import { interpolate, spring } from 'remotion';

const textAnimation = () => {
  const text = 'Hello World';
  const fontSize = 24;
  const duration = 10;

  const position = spring({
    from: { x: 0, y: 0 },
    to: { x: 100, y: 100 },
    duration,
  });

  const opacity = spring({
    from: 0,
    to: 1,
    duration,
  });

  const textAnimator = () => {
    const textKeyframes = [
      { time: 0, value: { x: 0, y: 0 } },
      { time: duration / 2, value: { x: 100, y: 100 } },
      { time: duration, value: { x: 0, y: 0 } },
    ];

    return (
      <Text
        text={text}
        fontSize={fontSize}
        x={position.value.x}
        y={position.value.y}
        opacity={opacity.value}
      />
    );
  };

  return (
    <Group>
      <textAnimator />
    </Group>
  );
};

export default textAnimation;
```

This code creates a simple text animation using the `spring` function from Remotion. You can customize the animation by adjusting the `position` and `opacity` values.

To add a blinking cursor, you can use the following code:

```jsx
import { interpolate, spring } from 'remotion';

const blinkingCursor = () => {
  const cursor = spring({
    from: { x: 0, y: 0 },
    to: { x: 100, y: 100 },
    duration: 10,
  });

  const opacity = spring({
    from: 0,
    to: 1,
    duration: 10,
  });

  const cursorAnimator = () => {
    const cursorKeyframes = [
      { time: 0, value: { x: 0, y: 0 } },
      { time: 5, value: { x: 100, y: 100 } },
      { time: 10, value: { x: 0, y: 0 } },
    ];

    return (
      <Group>
        <Rect
          x={cursor.value.x}
          y={cursor.value.y}
          width={10}
          height={10}
          opacity={opacity.value}
        />
      </Group>
    );
  };

  return (
    <Group>
      <cursorAnimator />
    </Group>
  );
};

export default blinkingCursor;
```

This code creates a simple blinking cursor animation using the `spring` function from Remotion. You can customize the animation by adjusting the `cursor` and `opacity` values.

To add a background animation, you can use the following code:

```jsx
import { interpolate, spring } from 'remotion';

const backgroundAnimation = () => {
  const noise = spring({
    from: { x: 0, y: 0 },
    to: { x: 100, y: 100 },
    duration: 10,
  });

  const opacity = spring({
    from: 0,
    to: 1,
    duration: 10,
  });

  const backgroundAnimator =

**Recipe for the Background Animation**

1. **Text Animator Setup**
	* Create a new text layer with the text "Again, you can apply this to any project."
	* Go to the Text Animator panel and add a new animator.
	* Set the animator type to "Scale" and set the ease to "Ease In" with a duration of 2 seconds (120 frames at 60fps).
	* Set the keyframes for the scale to 100% at frame 0 and 50% at frame 120.
2. **Masks**
	* Create a new mask for the text layer and set it to a "Rectangle" shape.
	* Set the mask's position to (0, 0) and size to (100, 100).
	* Set the mask's opacity to 0% at frame 0 and 100% at frame 120.
3. **Camera/Null Move**
	* Create a new null object and name it "Camera".
	* Set the null object's position to (0, 0, 0) and rotation to (0, 0, 0).
	* Set the null object's scale to (1, 1, 1).
	* Create a new camera and parent it to the null object.
	* Set the camera's position to (0, 0, 0) and rotation to (0, 0, 0).
4. **Motion Blur**
	* Enable motion blur on the camera by going to the "Camera" panel and checking the "Motion Blur" checkbox.
	* Set the motion blur duration to 1 second (60 frames at 60fps).
5. **Glow**
	* Create a new solid layer and name it "Glow".
	* Set the solid layer's color to a bright yellow (#FFFF00) and opacity to 50%.
	* Set the solid layer's position to (0, 0) and size to (100, 100).
	* Set the solid layer's glow to 10 pixels with a color of #FFFF00.
6. **Transitions**
	* Create a new solid layer and name it "Transition".
	* Set the solid layer's color to a bright blue (#0000FF) and opacity to 50%.
	* Set the solid layer's position to (0, 0) and size to (100, 100).
	* Set the solid layer's transition to a "Fade In" with a duration of 1 second (60 frames at 60fps).
7. **UI Mockup Handling**
	* Create a new solid layer and name it "UI Mockup".
	* Set the solid layer's color to a bright gray (#808080) and opacity to 50%.
	* Set the solid layer's position to (0, 0) and size to (100, 100).
	* Set the solid layer's UI mockup to a "Simple" UI with a duration of 1 second (60 frames at 60fps).
8. **Typography Sizes/Fonts**
	* Set the text layer's font to "Arial" with a size of 24 points.
	* Set the text layer's color to a bright blue (#0000FF).
9. **Background Animation**
	* Create a new solid layer and name it "Background".
	* Set the solid layer's color to a bright gray (#808080) and opacity to 50%.
	* Set the solid layer's position to (0, 0) and size to (100, 100).
	* Set the solid layer's animation to a "Fade In" with a duration of 1 second (60 frames at 60fps).

**Reproducing the Animation in Remotion**

```jsx
import { interpolate, spring } from 'remotion';

const background = spring({
  from: { opacity: 0 },
  to: { opacity: 1 },
  duration: 60,
  easing: spring.easing.easeInOut,
});

const text = spring({
  from: { scale: 1 },
  to: { scale: 0.5 },
  duration: 120,
  easing: spring.easing.easeInOut,
});

const mask = spring({
  from: { opacity: 0 },
  to: { opacity: 1 },
  duration: 120,
  easing: spring.easing.easeInOut,
});

const camera = spring({
  from: { position: [0, 0, 0] },
  to: { position: [0, 0, 0] },
  duration: 60,
  easing: spring.easing.easeInOut,
});

const glow = spring({
  from: { opacity: 0.5 },
  to: { opacity: 1 },
  duration: 60,
  easing: spring.easing.easeInOut,
});

const transition = spring({
  from: { opacity: 0 },
  to: { opacity: 1 },
  duration: 60,
  easing: spring.easing.easeInOut,
});

const uiMockup = spring({
  from: { opacity: 0.5 },
  to: { opacity: 1 },
  duration: 60,
  easing: spring.easing.easeInOut,
});

const typography = spring({
  from: { fontSize: 24 },
  to: { fontSize: 24 },
