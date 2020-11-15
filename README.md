## Heading Animation

Some explanation on how to create the animation is below. It's detailed so that
if you have errors you can find what's wrong. If you just want to copy it for a
project, you just need to do steps for Figma and HTML, the rest you can copy,
paste.



1. Figma
  - Open Figma, create a new draft and frame depending on the size screen you
    need it for.
  - Add a fill colour to the background so that it's not white so you can see
    the text you're about to write.
  - Create a text box, add whatever word, size and font you need
    (I used Robotto, 144)
  - Right click on the text and select Outline Stroke. You won't see a change
    but this will let you copy each letter as svg later on with seperate paths.
  - On the right, '+' stroke with white fill and increase the thickness
    (between 3-5 is good). The text should now have a white outline to it.
  - Click the '-' next to Fill. You should now have your text with only a white
    outline.
  - Finally, right click copy > copy as SVG

2. HTML
  - Paste into your HTML. You should have something similiar to the
    index.html in this folder. This will give you a svg block with 2 sections.
  - Delete everything inside the mask section so that you're left with
    1 path tag per letter.
  - You're going to iterate over each letter in JS so check that number of paths
    = number of letters.
  - Finally, add `id = "logo"` to the opening SVG tag. You'll use this to select
    with js.

3. CSS
  - Lines 1-17 are just there for centering the logo in the example so you can
    ignore this.
  - Line 18 dictates how long the text takes to fill, you can adjust the timing
    for your own project.
  - The keyframe with stroke dash offset is explained in JS section below.
  - Key frame fill dictates the fill colours which you can adjust depending on
    the project.

4. JS
  - First, you select each letter from the logo and iterate over each one. Set
    the initial time variable from when you want the anim to start.
  - For each letter add a strokedasharray which turns the outline into a dotted
    line. You want the dash to be the entire length of the letter
    (getletterlength)
  - The strokedashoffset moves the position of the dash. As the dash is entire
    length, if you set the offset to the entire length as well, this will mean
    there's no outline which is what you want to start.
  - The 'keyframe to' strokedashoffset is 0 in the css so once the animation is
    over, the big dash is back to just being the letter outline.
  - Add the transition so the dashoffset moves smoothly from the full letter
    length to 0.
  - Finally, increment the timing so each letter animates at a different time.










