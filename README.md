Magic 8 Ball [Web Version]
=======================
The magic 8 ball, yes, again, but now with a frontend built using the CreateJS and EaselJS frameworks...

# Installation

### On runnable.com:
Create a new node app, and from the terminal, enter or cut and paste the following commands, then press enter or return:
    
    git clone https://github.com/jfraboni/magic-8-ball-web.git spark && spark/setup.sh
    
...some text will fly by as the repository is cloned locally and the project is setup.

Great, you're set to roll!


# Frontend development

There's three components to our app: The HTML markup, some JavaScript that utilizes the animation framework of EaselJS, and a sprite-sheet, which is essentially a group of images mashed together into one larger image accompanied by a map of data which tells us where in the larger image each individual image resides.

**Setup the HTML**

We'll be using the `<canvas></canvas>` element, an element added with HTML5 that provides drawing API.  A canvas element will serve as the `stage` for all of our EaselJS objects and animation.  We will also need a `textarea` and `button`.

**TODO 1 :** Add all the HTML5 elements required for our app:

```javascript
<!-- TODO 1 : Add the HTML elements we need for our app -->
<canvas id="stage" width="470" height="470"></canvas>
<div>
    <textarea id="txtUserInput" rows="1" cols="74"></textarea>
</div>
<div>
    <button id="btnAsk">Ask Your Question...</button>
</div>
```

**Run the App** Go ahead and click run

...you should see a empty textfield and a button that says `Ask Your Question...`.  Great, let's move onto loading the sprite-sheet.

# Help Us Improve

Please help us improve our efforts to help you learn by taking a few moments to give us feedback:

[Feedback](https://docs.google.com/forms/d/1phvbnYuCX9o2KU_G4SMuhQJD9yDLQYeieIQ7E52T4sU/viewform?usp=send_form)

Thanks, you've helped us considerably!

# Other Resources

Continue your learning by visiting <a href="https://github.com/jfraboni/simple-node-app/wiki/Home" target="_blank">our JavaScript wiki</a>

And please visit <a href="http://operationspark.org" target="_blank">operationspark.org</a> to learn more about our project.


&copy; John Fraboni 2014