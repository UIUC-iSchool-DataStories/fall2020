---
title: Framing Devices
layout: lecture
---
<!-- .slide: class="titleslide" -->

# Framing Devices and Design

## Matthew Turk
## Fall 2020

---

# Today

1. Finding the story
   * Data
   * Plot
   * Characters
   * Narrative
2. Framing devices and design
   * Design for interactivity versus static
   * Guided vs unguided
3. Types of Stories
   * Interactive data-informed stories
   * Interactive data-driven stories
4. Javascript, and Doing D3 Together

---

## Finding the story

 > "But the numbers keep on circling me..."

Let's talk about explaining things.

---

## How do we tell stories?

 * Teller
 * Tale
 * Told

---

## Data Stories

Where does the data fit into this?

Where does the interaction fit into this?

---

## Informing versus Driving

Do you want your audience to be able to recreate your input data?  To make inferences?  Or is it appropriate to focus on conveying broad ideas, without one-to-one mapping of information to visualization?

Our stories must be *honest*.

How can we relate this to thinking about inductive as opposed to deductive storytelling?

---

## Framing Devices

Think of a video game, or a movie, where someone was introduced to something.

---

## Framing Devices

What do framing devices provide?

 * Context
 * Stability
 * Orientation

---

## Framing Devices: Context

<iframe seamless="seamless" style="width: 100%; border: none; display: block; max-width: 768px; height: 600px;" src="https://getyarn.io/yarn-clip/embed/cc875f97-6042-4c9b-861a-614c32cc08f2?autoplay=false"> </iframe>

---

## Framing Devices: Stability

<iframe width="896" height="504" src="https://www.youtube.com/embed/Fmeb-f4pthA" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

---

## Framing Devices: Orientation

<iframe width="896" height="504" src="https://www.youtube.com/embed/oEgO16JaW4Y" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

---

## Storytelling Form

 * Narrative
 * Navigable
 * Hybrid

---

## Style of Story: Navigable

Do we give the person control?  How much control?  What do we need to retain?

<ul>
 <li class="fragment"><b>Causality</b>: Do we want to start <i>en media res</i>? Are we just a bunch of events that happen to occur?</li>
 <li class="fragment"><b>Control</b>: How many degrees of freedom do we provide? When does it become confusing?  Is it sequential, random access, or a hybrid?</li>
 <li class="fragment"><b>Connection</b>: Does the experience (the teller) enable a connection between the data (the tale) and the viewer (the told)?</li>
</ul>

---

## Style of Story: Static

Things sit there.  People can explore with their eyes, but the reference points never change under their feet.

These can be effective, but can also be less visceral.

---

## Style of Story: Hybrid

A large-scale progression, coupled with intermediate diagrams that may be navigable.

---

## Style of Story: Examples

 * [Bloomberg 50](https://www.bloomberg.com/features/2019-bloomberg-50/)
 * [Figures in the Sky](http://www.datasketch.es/may/code/nadieh/) (and [write-up](https://www.visualcinnamon.com/portfolio/figures-in-the-stars))
 * [Selfie City](http://selfiecity.net/)
 * [Letter Frequency](https://public.tableau.com/en-us/gallery/frequency-letters)
 * [Legend of Nixon](https://twotone.io/examples/legend-of-nixon/)

---

## Designing Your Story

 1. What medium will you use?
    * How do you want people to "consume" it?
    * What are the pre-requisites?
    * What do you need to do to prepare it?
 2. What should it look like?
    * How "risky" should it be?
    * Is there a "visual language" you could use?
 3. Where are the dimensions?
    * What can change?
    * What can stay the same?
    * What can the audience control, and what can they not?

---

## You Can Do This

<p class="fragment">Yes, you can do this.</p>

<p class="fragment">Even the stuff that seems super technical and complicated.</p>

<p class="fragment">I wouldn't say this if it weren't true.</p>

---

## Resources

<ul>
<li class="fragment">There are tutorials out there.  Use these.</li>
<li class="fragment">Use templates.  Make them your own.</li>
<li class="fragment">Learn from others.  Ask questions.</li>
<li class="fragment">Find the fun things.</li>
<li class="fragment">Use stuff like <a href="https://iodide.io">iodide</a>, <a href="https://observablehq.com/">observable</a>, <a href="https://learning.oreilly.com/">safari</a>, <a href="https://github.com/">github</a>, and especially <a href="https://glitch.com/">glitch</a>.
</ul>

---

## Choosing a Medium

 * Will you be there?
 * How constrained is your story?
 * What technical abilities do you have?
 * How does the data interact?

---

## Technical Choices for a Medium

[Explorables explanations](https://explorabl.es/) has a collection of [tools](https://explorabl.es/tools/) we can explore.

[Kinetic Graphs](https://kineticgraphs.org/) allows you to define specific characteristics, thus enabling mathematical formulas to be manipulated.

[Observable](https://observablehq.com/) is a platform for exploring interactive notebooks, and is particularly well-suited to visualization and design projects.

[GitHub Pages](https://pages.github.com) is a straightforward way of creating HTML (or markdown) and placing it online.  This can include interactivity.

[Glitch](https://glitch.com/) is an environment for exploration of web development and applications which can have server-side components.

---

## Introduction to Javascript and d3

We are going to learn just a *little* bit about Javascript, and then we are going to talk about how we can construct [data-driven documents](https://d3js.org/) by hand.

<p class="fragment">The important thing here isn't what we are building, or the code we write.</p>

<p class="fragment">The important concept is that of binding data to representation.</p>

---

## Javascript in Ten Minutes

You can declare variables in Javascript implicitly or explicitly, depending on
how you want them scoped.

```
var myArray = [1, 2, 3, 4];
var myString = "Hello there!";
var myConcatString = "Hi " + "there " + 5;
var myObject = {'a': 1, 'b': 2, 'c': [1, 2, 3, 4]};
```

---

## Updating variables

If you have an array of objects, there are three very handy functions you can
utilize: `slice`, `forEach` and `filter`.  If you have an object, you can
update it either by accessing a property with a period (`obj.something`) or by
accessing it like you would a dictionary in python (`obj['something']`).

---

## Arrays: `filter`

```
var myArray = [1, 5, 1, 3, 50, 14, 2];
myArrayFiltered = myArray.filter(val => val > 2);
```

Note that here I'm using `=>` as shorthand for declaring a function.

---

## Arrays: `forEach`

To execute something on every value in an array, you can call `forEach` with a
function.

```
var myArray = [1, 2, 3, 4, 5];
myArray.forEach(val => console.log(val * 2));
```

---

## Arrays: `slice`

You can set a start and a stop on an array with a `slice` call:

```
var myArray = ["Hello", "I", "am", "here", "now"];
myArray.slice(3).forEach(word => console.log(word));
```

---

## d3 and Data-Driven Documents

We are now going to try out a little bit -- seriously, not very much at all! -- of [d3](https://d3js.org/).

The best place to try this out is at [ObservableHQ](https://observablehq.com/).
