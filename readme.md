## Fronteers 2017
My notes on [Fronteers 2017](https://fronteers.nl/congres/2017). Don't mind any spelling mistakes, and any potential misinterpretations are all mine :)

---

**Day 0**
- [Val Head - The Web In motion](#val)

**Day 1**
- [Niels Leenheer - Don't Panic](#niels)
- [Jessica Rose - Impostor Syndrome and Individual Competence](#jessica)
- [Umar Hansa - A Modern Front-end Workflow](#umar)
- [Yoav Weiss - Caching all the way down](#yoav)
- [Alice Boxhall - Debugging Accessibility](#alice)

**Day 2**
- [Alicia Sedlock - The Landscape of Front-End Testing](#alicia)
-

---

<a name="val"></a>
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

---

### Day One

---

<a name="niels"></a>
#### Niels Leenheer: Don't Panic
> Users over authors over implementors over specifiers over theoritical purity.

> Don't develop for browsers, develop for the web.

---


<a name="jessica"></a>
#### Jessica Rose - Impostor Syndrome and Individual Competence
Our brains are terrible at self-assessment. This can be very demotivating. Your brain uses bad data to build worse conclusions that it becomes really attached to: enter impostor syndrome.

If you're getting messages that you're not in a space that belongs to you, you internalize those.

What is technology doing to impostor syndrome? Social media can make it worse. Technology invites us to compare our real lives to someone else's Best Of Hits.

How can we make it better for others?
- Never tell anyone else they have impostor syndrome. Don't override someone's concerns with just "oh, it's just impostor syndrome".
- Give positive meaningful and actionable feedback.
- Talk about your own feelings and fears when you feel comfortable doing so.

Fixing it for yourself:
- Take on positive feedback and accurately assess yourself: you can outsource the latter (tests, teaching, write articles).
- Interrupt the "oh god they're going to find out" process. Check in with yourself periodically. Take care of yourself and do the thing that chills you out.
- Keep track of what you learn over time, and look back periodically.

What if impostor syndrome is just your brain telling you in a terrible way that you're actually doing fine?

* http://jangosteve.com/post/380926251/no-one-knows-what-theyre-doing

---

<a name="umar"></a>
#### Umar Hansa - A Modern Front-end Workflow
*The audience can expect to learn hidden DevTools secrets but also how to adopt a modern development and debugging workflow. This talk is important for any web developer who wants to understand and debug the internals of a webpage quickly and with ease.*

* https://moderndevtools.com/

In DevTools: CMD+P for searching/screenshots.

CSS Grid devtools are coming to Chrome!

Cleaner logs with log management: console.context.

---

<a name="yoav"></a>
#### Yoav Weiss - Caches all the way down
*The fastest resource download is the one never made. Caching is a great way to ensure your content is positioned as close to your users as possible and that your repeat visitors get instant access to your content. Developers can impact the behavior of network and browser caches, improving content caching and ensuring it’s always as available as it can be, but caching semantics in HTTP can be confusing, which means that most content on the web today is not properly cached. Yoav Weiss explores HTTP cache semantics, strategies, browser internal caches, and service workers and explains how serve your content fast and fresh.*

Cache: a hiding place for a computer program where they can keep data for later use. How does the computer decide when to invalidate this data? When do you evict data? You must be sure that data you'll put in, is more valuable the data that gets removed is less useful. How do you ensure you're serving fresh content?

Cache invalidation is hard because you're basically having to predict the future.

Despite the fact you can't always get it right, we use caching all the time.
- L1 (0.5 nanosec)
- L2
- L3
- RAM
- SSD
- HDD Seek
- Network (150 millisec)

Avoid fetching from disk or network, slow and unpredictable.

If you reduce latency for each request, you'll exponentially speed up your application. As frontend devs, latency is our enemy and caching is our weapon.

##### What does caching on the web look like?
1. A request for a resource (script, image..) is created inside the rendering engine. A request can created in different ways: an API explicitly requests a resource, or a user just browses to a page and HTML must be loaded.
2. It looks in the memory cache first (short-term memory cache) first. Once the render is destroyed, this short-term cache disappears. Memory cache is complex when it comes to request matching. It does not permit mixing of types, and requires strict type matching. There is also credential checking. At the same time, it does not enforce HTTP caching semantics. Even if the resource is non-cacheable, it can still be served as part of the memory cache. This is OK though, because the memory cache is volatile by nature.
3. All this behaviour is in specs. We don't do a good job of really understanding it though.
4. The request get passed along. It now appears in DevTools. It continues to the Service Worker. These have their own separate cache. They have an explicit cache with their own API. It's slightly unpredictable. It can return anything as a response, even create their own. This logic is created by the dev, not the browser.
5. The first place to look for a resource is the http cache. It's very strict. But it can mix resource types, i.e. can return an image from a script request. It's persistent storage: data is stored to disk. So this can be quite slow compared to getting something from the memory cache.
6. No response? Then we move on to the network. But before that, there is one more step: the push cache (H2 Push). Unclaimed streams as part of the H2 connection.
7. Still nothing? We move on to the network. Latencies are dependent on many factors. ISP, edge, internet, reverse proxy..it's a scary place. Packet rates differ a lot. What can devs do to lower latency? This is where the edge cache comes in. By sitting as close as possible to your ISP's gateway, you don't have to travel as far for a resource.
8. If the last line of caching does not work, we have the origin server. If the server does not have the resource, it'll return an error.


The first thing to know about HTTP caching is that the resource URL is key. It's what used in the cache to find the request. If you request the same URL twice, the second request could get the response as a cached resource. A key concept is freshness: how long can a cache serve a resource without revalidating it? THis is where predicting the future part comes in. How do we define freshness?

`Cache-Control: max-age=3600;`: we tell The Internet we're not going to change anything in the next hour. But what if we do change something? We'll risk serving outdated content to users.

Validators are HTTP responses such as `Last-Modified` or `ETag`. This enables the browser to validate resources with conditionals such as `If-Modified-Since`. Super helpful, but still has a cost.

Scope is another aspect of HTTP caching. Do we cache in the browser? On a public network? What do we do with private information? That's where `Cache-Control` directives come in too: `public`, `private`.

Cachability directives can tell the cache whether the resource is cacheable or not. `must-revalidate` means the resource will not be revalidated as long as it's fresh, but must not be served stale. Usecase: only when the content you serve will really be invalid after the freshness runs out. `no-cache` will actually cache: but it won't serve resources from the cache, unless it's revalidated. With the directive `immutable`, even a hard refresh from the browser won't clear the cache.

A related HTTP response header is `age`: how long has this resource been sitting in cache? `key` is a recent proposal that enables us to define more granular cache keys, ex. `Key: Width;partition=300:600:1200`.

##### Caching best practices
- Give your files a unique hash, and then make sure they never require validation. If you change the file, also change the hash.
- For everything that is not immutable, serve it as either `no-cache` or `max-age=5`.
- Everything else is a gamble: we can't predict the future. Anywhere between the above extremes is a bet..or is it?

Enter CDNs: hold 'til told. Content is immutable at the edge, but it has some explicit directives that devs can access, so they can remove cache through an API call.

Also, service workers to the rescue. Where do they live? Why is it faster than HTTP? It lives on disk, it's persistent. It lives closer to where the request is created. Most of the advantages aren't necessarily because it's faster, but because it's more reliable: you control the eviction and decide when a resource is important and should stay.

##### Take-aways
- Caching is extremely important for performance.
- It can be complex and daunting.
- Browsers have a lot of internal caches. Browser caches are not all spec'ed.
- HTTP caching pattern concepts: immutable content and always revalidate.
- Service workers offer a lot of new opportunities here.

* https://www.phpied.com/update-a-far-future-expiring-component/

___

<a name="alice"></a>
#### Alice Boxhall - Debugging Accessibility
Disability is an interaction between a person's condition and their environment. The web is a visual and pointer-based medium. This can be disabling. Any user interface requires an ability from a user, to varying degrees. The less an interface requires of its user, the more accessible it is.

- Perceivable
    - Do you require your users to have perfect vision?
- Operable
    - Do you require your users to have perfect motor skills?
- Understandable
    - Do you require a high degree of language ability?
- Robust
    - Compatibility with current and future user agents.

a11y experts understate the costs involved with creating robustness. a11y makes experiences better for everyone, but that is not always true for robustness. Not everyone gains something by a robust page.

* https://www.ensie.nl/paul-van-den-dool/affordance

(Some) disabled users interact with assistive technology, not with your UI. The assistive technology interacts with the UI.

ARIA allows you to modify the semantic meaning of elements.

---

### Day Two

---

<a name="alicia"></a>
#### Alice Sedhall - The Landscape of Front-End Testing

Developers have a social responsibility. When we're putting people's medical and banking records on the web, we need to make sure we're accountable for the the code we write, and that this code is maintainable. This is where testing comes in. There are different types of frontend testing:

1. Unit
2. Integration
3. Acceptance
4. Visual regression
5. Performance
6. a11y

Unit tests are for ensuring small pieces of code work as expected. Will a single function always produce the result we expect?

Integration tests: how are pieces of an application working together? If you make changes to certain modules that other parts of your code are dependent on, an integration tests helps you to avoid breaking those other parts.

Acceptance tests: make sure we can accomplish major tasks. We simulate user behavior and interact with our application, see what happens. Example: a user trying to sign up for something.

* Unit testing tools: Jasmin, Mocha, Chai, Jest, QUnit, Unit.js, webdriver.io.
* Integration and acceptance testing tools: jasmine-integration, Selenium, Nightwatch, Karma.

As frontenders, we have an interface we can visually test. The latter three types of test are rising in popularity, especially visual regression testing. This will look for inconsistencies in the view: what has changed, and is the difference what you expected it to be? You can test full pages, or just components. You can set tolerances for changes ("alert us of any change, or only if it's moved by more than 5 pixels").

a11y tests compare your site against a11y standards. They'll look at your code, and check if it's compliant with the standards. You can integrate these tests with Gulp or Webpack, or even run them through the CLI.

Performance tests

* Regression testing tools: Wraith, Casper (PhantomCSS), Percy, BackstopJS.
* a11y tools: Pa11y, Chrome Accessibility Audit, a11y.
