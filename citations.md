## scrolling

I asked ChatGPT the Following:

"I am working in HTML, CSS, and D3. I want to set up a scroll on my webpage similar to the New York Times so that as the user scrolls, they new information appears. Can you help direct me to what sort of functions or examples I can look at?"

It provided:

Good question. What you describe — a webpage that reveals or changes content as you scroll (like many longform interactive articles on The New York Times) — is often called “scrollytelling” or scroll-triggered storytelling/animations. 
Go Make Things
+2
Erik Driessen
+2

Since you already use HTML, CSS, and D3.js, you’re well positioned to build that kind of interactive experience. Below are some techniques, libraries, and concrete examples you can explore — and how they map to what you already know.

✅ Key Techniques & Patterns

Scroll-driven animations — using the scroll position as input to animate or reveal elements (fade-in, transitions, charts updating, etc.). 
MDN Web Docs
+2
Chrome for Developers
+2

“Sticky” or “pinned” elements — keep certain elements (e.g. a chart or image) fixed in the viewport while other content scrolls; then change that element (e.g. update a chart) as you pass through scroll “steps.” This is common in scrollytelling. 
GitHub
+2
vallandingham.me
+2

Scroll-event or observer based triggering — detect when a scroll passes certain thresholds or when elements enter/exit viewport; then trigger transitions or updates (e.g. change a D3 chart) accordingly. 
Go Make Things
+2
vallandingham.me
+2

Progressive storytelling structure — you segment your page into “steps” or “scenes” (text + data-visualization), and as the user scrolls through each step, you update visuals based on scroll position or which step is ‘active’. 
Erik Driessen
+1

Optionally: CSS-based scroll-linked animations — modern browsers support scroll-driven animations via CSS (e.g. scroll timelines, view-timelines), which can give smoother, more performant scroll effects without heavy JavaScript. 
MDN Web Docs
+1

🛠️ Libraries / Tools & Example Codebases to Use

Because you use D3, pairing it with a small scroll-triggering helper makes things much easier. Here are popular choices:

Library / Example	Description / Why It’s Useful	Notes
Scrollama.js	A lightweight, vanilla-JS library for “scrollytelling” — detects when defined “steps” scroll into view and triggers callbacks. Great for triggering D3 updates as you scroll. 
Go Make Things
+1
	Works well with plain HTML/CSS + D3; Intersection Observer under the hood, with fallback. 
Go Make Things
+1

A demo repo: scrollytelling-scrollama-d3-demo (on GitHub)	Demo combining Scrollama + D3 to build a scroll-driven data story: shows how to structure HTML, CSS, and JS for this pattern. 
GitHub
	Good starting point for you: includes html, style, scroll-handling, and D3 animation code. 
GitHub

Plain JS “scroller” pattern / tutorial: scroller.js (from a long-standing tutorial)	Shows how to manually detect which section is “active” (based on scroll), get bounding positions, and switch visuals accordingly. Good to understand the core mechanics. 
vallandingham.me
	Classic approach if you prefer minimal dependencies.
CSS Scroll-Driven Animations (with Scroll-Timelines / View-Timelines)	Lets you create animations tied to scroll position in CSS — so transitions run off the main thread, smoother performance, and less JS required. 
MDN Web Docs
+1
	Worth a look if your animations are simple (opacity, translate, etc.) and you want performance benefits.
📚 Recommended Reading / Tutorials to Get Started

The post “An introduction to scrollytelling: data storytelling using scrollama.js, d3.js and html/css” — very approachable explanation + guidance on building interactive scrollytelling with D3. 
Erik Driessen

The “scrollytelling-scrollama-d3-demo” repo — inspect the HTML/JS/CSS setup to see how sections, scrolling triggers, and D3 visual state changes are coordinated. 
GitHub

The tutorial “So You Want to Build A Scroller” — gives details on the math behind detecting scroll positions, section offsets, and switching states, using vanilla JS + D3. 
vallandingham.me

The CSS-based guide for scroll-driven animations — helpful if you want to minimize JS and leverage newer browser features. 
MDN Web Docs
+1

🎯 How to Get Started (for YOUR D3 + HTML + CSS Setup)

Here’s a minimal plan you could follow:

Sketch out your “story”: divide into logical sections/steps, each with text + maybe a D3 chart or visualization.

Build a static version: write HTML + CSS so that each section corresponds to a container (e.g. <div class="step">).

Add scroll-trigger logic: integrate Scrollama (or write your own “scroller.js” logic) to detect when each step becomes active — call a callback on enter/exit of each step.

Use D3 to draw or update SVG during those callbacks: e.g. animate charts, show/hide elements, update data, etc.

(Optionally) polish with CSS scroll-driven animations for simpler transitions (fade-ins, position shifts) to improve performance and smoothness.

Test across browsers / screen sizes — especially check how it behaves if user scrolls fast, or loads in the middle of the article.

If you like, I can pull up 5–10 live scrollytelling examples (with codeSandbox / GitHub links) that are built on D3 + scroll-trigger, so you can inspect real-world implementations.
Do you want me to build that list for you now?

----

I responded "yes" to examples and it gave the below:

Cool — here’s a curated list of live scrollytelling / scroll-driven storytelling examples and codebases (many using D3 or similar) that you can dig into to learn how to build a scrolling interactive like The New York Times style. I arranged them roughly from “simplest / minimal” to “full-blown data-story projects,” so you can pick based on how much you want to adapt vs. study.

🔗 Example Repositories & Demos for Scrollytelling + D3 (or Vanilla JS)
#	Project / Demo	What’s Good / What You Learn
1	Scrollama — example/demo pages + library repo	This is one of the most popular light-weight JS libraries for scrollytelling. It uses IntersectionObserver, and is well-suited for pairing with D3 or raw JS. The examples cover basic step-triggers, sticky graphics (side or overlay), progress-callbacks, custom offsets, etc. 
GitHub
+2
alidep.github.io
+2

2	scrollytell — minimal mobile-friendly scrollytelling examples	A very simple, straightforward approach that works even without D3. Easy to grasp for a first experiment: minimal boilerplate, good for testing scrolling + reveal behavior. 
Google GitHub
+1

3	ScrollyTeller (from ihmeuw / GitHub) — JS library for scroll-driven data stories	Higher-level abstraction: supports separation of “narration” text blocks + corresponding graphs/charts triggered via scroll. Handles layout, data loading, event triggers — nice if you want a modular, maintainable structure for a longer story or multi-section page. 
GitHub

4	scrollytelling‑scrollama‑d3‑demo — a concrete demo combining Scrollama + D3	A real, working example of a “scroll story + data viz + D3 transitions.” It shows how to coordinate HTML steps, CSS for layout, and D3 animation updates based on scroll events. Perfect “from-template to working demo” for you to fork and adapt. 
GitHub
+1

5	Bare-bones example: simplified‑scrollama‑scrollytelling — vanilla JS + minimal overhead	If you don’t need D3 or fancy charts, this shows the absolute minimal setup for scrollytelling using Scrollama — educational for understanding the core scroll-trigger logic before layering D3 on top. 
GitHub
+1

6	A blog-style scrollytelling example: “Titanic data” scroll-story using D3 (from a tutorial post)	Useful if you prefer reading through a blog post (less boilerplate) — shows how someone built a scrolling data-driven narrative with D3, starting from a familiar dataset. A nice learning-by-doing resource. 
Medium
🎯 What to Explore in Each Example: What You’ll Learn

With Scrollama — how to break your document into “steps,” define callbacks for when a step enters/exit the viewport or its progress updates, and hook those into D3 chart updates or transitions.

With scrollytell — simpler scroll-linked behaviors, good for reveal/fade-in/out or fixed “sticky” charts without complex state management.

With ScrollyTeller — how to design more complex, modular “data stories” where each scroll-section links to different datasets or charts; how to manage narrations vs. visuals.

From the scrollama + D3 demo repo — exactly how HTML, CSS (including sticky positioning) and JS are structured together for a working integration; good template to fork.

From minimal or bare-bones versions — a clear view of the “core” of scroll-triggering logic: viewport detection → trigger → update/transition.

From real-world “data-story” blog-style examples — what storytelling pacing, layout, data binding, and user experience look like in a full scrollytelling article.

🧪 How I’d Explore Them If I Were You (Step-by-Step)

Start with scrollama + simplified-scrollama examples — build a simple static page with 3–4 text sections and maybe a colored <div> that changes on scroll. Focus on understanding how step detection works and how to trigger JS callbacks.

Swap out the colored <div> with a simple D3 chart (even a basic bar or circle) and animate attributes (color, position) based on step triggers — practice combining scroll + D3.

Clone the scrollama + D3 demo repo, run it locally — study how its HTML, CSS, and JS are organized. Try modifying data or animation logic to see how behavior changes.

Explore ScrollyTeller if you anticipate a multi-section story — maybe wire up multiple charts with different datasets, and practice triggering different visuals for each narration block.

Review blog-style examples (e.g. the “Titanic” story) — to see storytelling flow: how authors structure narrative + visuals, how many “steps” per chart, how they pace user experience via scrolling.

If you like — I can also pull up 5–10 real-world “published” journalism-style pages (like what you see on big media sites) that use these techniques + D3 / scrollama: that way you can see what it looks like to end-users, not just code.
Do you want me to build that “real-world published examples” list for you now?