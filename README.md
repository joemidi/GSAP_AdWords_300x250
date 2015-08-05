# GSAP_AdWords_300x250
Just a test to see how to use GSAP in Google Web Designer

After a little testing, this is pretty much the same as how you would create a banner in Flash.
1. Lay everything out on the stage.
2. Import Greensock
3. Write your animation code.

## Layout
Use the design interface and lay everything out as you want it, making sure to rename all the ID's in the properties panel.

## Plug-in the GSAP code
Switch to design mode and you'll see all the HTML.
We want to add the TweenMax.min.js to the setup, I've already added that file to the assets library.

Using the same syntax we can load up the JS in the same manner.
```
104	  <script data-source="assets/TweenMax.min.js" data-version="1.17.0" type="text/javascript" src="assets/TweenMax.min.js"></script>
```

## Run the animation
A GWD banner will start when it's ready to fire off this function `gwdAd.initAd();` on line 144. So we'll put a call to our GSAP animation after that.

```
//Starting from line 152
function animateBanner() {
	var tl = new TimelineLite();
	tl.from(['#joe_midi', '#balloons'], 1.5, {
	    alpha: 0
	  })
	  .to('#balloons', 1, {
	    y: "-=200"
	  })
	  .staggerFrom(['#copy1', '#copy2', '#copy3'], 1.5, {
	    x: "-=250",
	    ease: Elastic.easeOut.config(1, 0.3)
	  }, 0.5);
}
```