# Pure CSS - Sphere
## Tutorial

Let’s learn how to create a cute little sphere using only HTML/CSS, without SVG or images — just pure code.

Let’s think like programmers and analyze how to solve this problem:


1. Objective: Create a sphere using only CSS

So first, what is a sphere?  Literally, a sphere is a 3D circle. Visually, when we talk about illustration, a sphere is a circle that simulates three-dimensionality.

This can be done using lines or a wireframe:

<img src="assets/img1.png" alt="Sphere wireframe example">


Or through light and shadow, positioning shapes of different tones and forms to simulate how light interacts with a sphere.

<img src="assets/img2.png" alt="Sphere with light and shadow">

With just one circle and three tones, we can create a sphere. Now let’s organize the problem-solving steps:

1. Create a circle  
2. Apply a shape to represent the light  
3. Apply a shape to represent the shadow  

Let's start by creating a `<div>` and giving it the class `sphere`.  
This `div` is the shapeless and colorless mass that we will style to become the sphere.

<img src="assets/img3.png" alt="first code">

We’ll set the background to black, turn the `<body>` into a flex container to center the sphere both horizontally and vertically, and set the body's height to 100% of the viewport height.

<img src="assets/img4.png" alt="body code">

Result:

<img src="assets/img5.png" alt="first result">

Now let’s make the sphere:

- Select the element with the class `sphere`  
- Set its size to a 200x200px square  
- Round the corners so the square becomes a perfect circle (turning the `div` into a circle)  

The most important part:

`background: radial-gradient(circle at 35% 35%, #4eb1ff 40%, #003366 41%);`

This applies a radial gradient that simulates light and shadow:

- `circle` – circular shape
- `at 35% 35%` – the light source is placed 35% down and 35% right from the top-left corner
- `#4eb1ff 40%` – light color goes up to 40%
- `#003366 41%` – dark color starts right after, creating a sharp cut between light and shadow

Another important element in pure CSS art is `box-shadow`.

`box-shadow: inset -20px -20px 40px rgba(0, 0, 0, 0.676);`

This creates an inner shadow inside the sphere:

- `inset` – makes the shadow internal
- `20px -20px` – the shadow is pushed up and to the left
- `40px` – makes it very diffuse
- `rgba(0, 0, 0, 0.676)` – semi-transparent black color

To finish this part, we add: `position: relative`

We apply a relative position so the glow we’ll apply later can be positioned relative to `.sphere`.

<img src="assets/img6.png" alt="sphere code">

Result:
<img src="assets/img7.png" alt="second result">

Let’s finish by applying the glow:

<img src="assets/img8.png" alt="sphere after">


- `.sphere::after {` seleciona o pseudo-elemento `::after` da `.sphere`. A pseudo-element is a keyword added to a selector that lets you **style a specific part** of an element, or **inject extra elements** for decoration. The most commonly used ones are `::before` and `::after`.
    - `::before`  inserts content **before** the element's actual content
    - `::after`  inserts content **after** the element's actual content
- `content: "";` is required for the pseudo-element to appear
- `position: absolute;`  position: absolute; Positions this pseudo-element absolutely inside the .sphere. This only works because .sphere has position: relative, making it the reference point for positioning.
- `top: 25px; left: 25px;` places the glow 25px from the top-left.
- `width` and `height` of 40px make it a small circle
- `border-radius: 50%;` makes it perfectly round
- `background: rgba(255, 255, 255, 0.4);` gives it a translucent white color
- `filter: blur(2px);` softens the glow for realism

Result:

<img src="assets/img9.png" alt="final result">

I became interested in this after discovering the work of Diana Adrianne Smith and her wonderful pure CSS illustrations, so I wanted to play a little with this unique type of art.
I don’t know if I’ll create projects as impressive as hers, but I think practicing this is a fun way to learn CSS.

To absorb this knowledge, I recommend you experiment with different colors and light directions.
