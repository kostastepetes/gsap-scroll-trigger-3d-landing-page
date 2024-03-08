This landing page is using the GSAP (GreenSock Animation Platform) library to create a parallax effect on a set of slides based on the scroll position of the page.

1. **GSAP Plugin Registration**:
   ```javascript
   gsap.registerPlugin(ScrollTrigger);
   ```
   This line registers the ScrollTrigger plugin from GSAP, which is used to trigger animations based on the scroll position.

2. **Event Listener**:
   ```javascript
   window.addEventListener("load", function () { ... });
   ```
   This code waits for the page to fully load before executing the script inside the event listener. This ensures that all elements on the page are loaded before the script runs.

3. **Variable Declarations**:
   ```javascript
   const slides = gsap.utils.toArray(".slide");
   const activeSlideImages = gsap.utils.toArray(".active-slide img");
   ```
   These lines create arrays containing references to all elements with the class "slide" and "active-slide img", respectively. These elements are the slides and images that will be affected by the parallax effect.

4. **Helper Functions**:
   - `getInitialTranslateZ(slide)`: This function calculates the initial translateZ value of a slide. This value is used to determine the initial position of the slide in the z-axis.
   - `mapRange(value, inMin, inMax, outMin, outMax)`: This function maps a value from one range to another. It's used to adjust opacity based on the position of the slide in the z-axis.

5. **Main Logic**:
   - The script iterates over each slide using `slides.forEach((slide, index) => { ... });`.
   - Inside the loop, a ScrollTrigger is created for each slide using `ScrollTrigger.create({ ... });`.
   - The `onUpdate` callback of the ScrollTrigger is where the main animation logic resides.
   - The progress of the scroll trigger is used to calculate the position of the slide in the z-axis (`currentZ`) and adjust its opacity accordingly.
   - The position and opacity of the slide are updated using CSS `style` properties.
   - Additionally, the opacity of the associated active slide image is animated based on the position of the slide in the z-axis.

Overall, this project creates a parallax effect where the slides move and fade based on the user's scroll position, and the opacity of associated images changes accordingly.
