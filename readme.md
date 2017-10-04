## Fronteers 2017
My notes on [Fronteers 2017](https://fronteers.nl/congres/2017). Don't mind any spelling mistakes, and any potential misinterpretations are all mine :)

### Day 0: Workshop Val Head: The Web In Motion
*A full-day deep-dive into modern web animation techniques with one of the world’s pre-eminent experts. Val Head will guide you through the intricacies of animation on the Web, vitally focussing on CSS, JS and SVG. This essential training will provide you with a solid overview of the possibilities to help you and your team successfully leverage Web animation in your projects.*

#### Classic Animation Theory
There are 12 classic animation principles. Adhering to these principles lowers the chance of an animation feeling "wrong", or just off. It's not an ordered list of steps to take, you don't need to use all of them at the same time. They are things to focus on when making an animation.

- Timing and spacing. The only way to get good at timing is to practice: more art than science. Timing: the amount of time it takes for an action to happen: duration in CSS. Spacing: the changes in speed over the duration of the action's timing: easing in CSS (ease-in, ease-out, et cetera: all cubic bezier curves). Makes animated objects appear to obey the laws of physics. Establishes mood, emotion and reaction: personality.
- Mass and weight.
- Follow through / overlapping action. Not everything comes to a stop at once, helps giving the impression that a thing is obeying the laws of physics.
- Anticipation: a little hesitation before the main movement, like the thing is preparing or getting ready for the main movement.
- Arcs. Organic movements typically don't follow straight lines of motion. Pretty much any natural movement has an arc to it, whereas a computer chooses the most efficient way. Therefore, coding an arc is harder than manually animating an arc.
- Secondary action: an additional action to the scene that supports the main action. See: claps on Medium and likes on Twitter.
- Exaggeration. The truth, but more extreme. Actions are made bigger and more drastic for greater effect and impact.
- Appeal. The charisma of the action. Something that makes you like or appreciate the animation. Sometimes it works, sometimes it doesn't: the good design of animation. You want it, but how to get to it is not a straightforward process.
- Squash and stretch. This is hard by hand, but easy by computer. Giving a thing a sense of weight and flexibility. Objects tend to change shape as they move depending on inertia and the elasticity of what they're made of. It's important to maintain volume of the object.
- Staging. Directing the audience's attention, and making it clear what is of greatest importance in a scene.
- Choreography. A lot of the classic principles focus on one animation, but generally we'll work with multiple animations. So we also need to think about how these animations work together. Some helpful rules:
 - Similar objects animate in similar ways. People trying to make things "interesting" ignore this, it just causes chaos and confusion.
 - Entrance informs exit. Not everything has to leave the way it came in, but it's good to have some consistency. If a modal comes up from the bottom, it makes sense it goes down (or up) the same way when leaving. It doesn't make sense if it leaves the page on the right-hand side.
 - Match velocities. You might think having the same duration everywhere is good, but it's better to match velocity, not duration.
 - Consistent or cohesive? Consistency suggests you're doing the exact same thing over and over again. However, it's okay if things are not always consistent. They have do be cohesive however. Animations don't have to be all the same, but they must have things in common.
- Continuity. Visual continuity is important. Reuse elements between views. Why should it leave the screen just to come back on again? We don't have to take everything out and put it all back again.

#### Animation with CSS
We have transforms, transitions and keyframes animations. Lots of words for ..animation? The terminology/syntax can be very confusing.

- Transforms: allow you to modify the coordinate space of the CSS visual formatting model: change the way the DOM object looks. Translate, rotate, skew, scale.. See [MDN](https://developer.mozilla.org/nl/docs/Web/CSS/transform) for the full list. Transforms compound on top of eachother.

- Transitions: how you make animations. You need a point A and a point B, and a duration.

- Keyframes: you need a named set of keyframes to assign, the animation name, and a duration. Keyframes are essentially a list of things to happen. You need to name them, otherwise you can't reference them (i.e. use them).

#### Animation with SVG
We have three choices: SMIL, CSS, JavaScript. Unfortunately, SMIL is being deprecated, and there is no IE support.

CSS transitions and keyframe animations can be applied to elements within SVG as well, but only a limited number of SVG presentation attributes are accessible as CSS properties. CSS transforms are not supported in Edge, but they're thinking about it. But fills and transforms can get you really far. If a little bouncy non-critical arrow doesn't work in IE, that's fine (progressive enhancement!).

Most important part of working with SVGs: all paths must be named after what they represent, or you'll have a hard time figuring out what path corresponds to which element in the SVG. If you have a path that represents 'cloud', don't name it 'svg-1'.

#### Animation with JS
JS can access native SVG properties. Which means you can get anything from an SVG. It has better browser support than CSS, but there are a bunch of cross-browser issues (of course).

#### Web Animation Performance
Browsers can efficiently transition: size (transform: scale), position (transform: translate), rotation (transform: rotate) and opacity. The reason they're efficient is because when the browsers sees them, the browser does not have to repaint or re-layout. See [CSS Triggers](https://csstriggers.com/):

*Changing transform does not trigger any geometry changes or painting, which is very good. This means that the operation can likely be carried out by the compositor thread with the help of the GPU.*

Margin is a more expensive property to transform: it forces the browser to repaint, relayout and re-composite.

- JavaScript: sorting data, adding elements, causing change
- Style: figuring out which CSS rules apply to which elements
- Layout: calculate the size changes of styles
- Paint: filling in the pixels
- Composite: putting everything in the correct layer order

#### Resources
* https://en.wikipedia.org/wiki/12_basic_principles_of_animation#The_12_Principles_of_Animation
* http://the12principles.tumblr.com/
* http://motionandmeaning.io/episode04.html
* https://www.dropbox.com/s/3d4jsdon05iq3gz/WAW%20Classic%20principles.pdf?dl=0


* https://dev.opera.com/articles/understanding-the-css-transforms-matrix/
* http://meyerweb.com/eric/tools/matrix/
* http://bouncejs.com/


* https://codepen.io/valhead/pen/oXNaBW
* https://www.justinmccandless.com/post/making-sense-of-svg-viewboxs-madness/


* https://greensock.com/ease-visualizer


* https://aerotwist.com/blog/on-translate3d-and-layer-creation-hacks/
* https://www.sitepoint.com/introduction-to-hardware-acceleration-css-animations/
* https://dev.opera.com/articles/css-will-change-property/
* https://www.udacity.com/course/browser-rendering-optimization--ud860
* https://developers.google.com/web/fundamentals/performance/rendering/stick-to-compositor-only-properties-and-manage-layer-count
