Magic 8 Ball [Web Version]
=======================
The magic 8 ball, yes, again, but now with a frontend built using the CreateJS and EaselJS frameworks...

# Installation

### Locally:
From the terminal, enter or cut and paste the following commands, then press enter or return:
    
    git clone https://github.com/jfraboni/magic-8-ball-web.git
    
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
    <button id="btnAskQuestion">Ask Your Question...</button>
</div>
```

**Run the App** Go ahead and click run

...you should see a empty textfield and a button that says `Ask Your Question...`.  Great, let's move onto loading the sprite-sheet.

**TODO 2 :**
```javascript
// other code...

// TODO 2 : Create some DOM element variables //
var answers = JSON.parse(document.getElementById('answers').innerHTML).answers;
var stage = new createjs.Stage('stage');
var btnAskQuestion = document.getElementById("btnAskQuestion");
var txtUserInput = document.getElementById("txtUserInput");


// other code...
```


**TODO 3 :**
```javascript
// other code...

// TODO 3 : Add a listener to the tick event to redraw the stage //
createjs.Ticker.addEventListener("tick", stage);

// other code...
```

**TODO 4 :**
```javascript
// other code...

// TODO 4 : Create and add to the stage the header //
var txtHeader = initHeader();
stage.addChild(txtHeader);

var magicEightBall = initMagicEightBall();
stage.addChild(magicEightBall);

var txtInstruction = initInstruction();
stage.addChild(txtInstruction);


// other code...
```

**TODO 5 :**
```javascript
// other code...

// TODO 5 : Initialize the response text //
function initResponse() {
    var txtResponse = new createjs.Text("", "25px Arial", "#ff7700");
    txtResponse.textBaseline = "middle";
    txtResponse.textAlign = "center";
    txtResponse.x = stage.canvas.width / 2;
    txtResponse.y = stage.canvas.height / 2 + 15;
    return txtResponse;
}

// other code...
```

**TODO 5.a :**
```javascript
// other code...

// TODO 5.a : Create and add to the stage the response //
var txtResponse = initResponse();
stage.addChild(txtResponse);

// other code...
```

**TODO 6 :**
```javascript
// other code...

// TODO 6 : Handle the valid question by running the ask animation //
txtUserInput.disabled = true;
magicEightBall.addEventListener("animationend", onAskAnimEnd);
magicEightBall.gotoAndPlay("ask");

// other code...
```

**TODO 7 :**
```javascript
// other code...

// TODO 7 : Randomly assign an answer to the response text object //
txtResponse.text = answers[randomNumberBetween(0, answers.length-1)].value;

// other code...
```

**TODO 8 :**
```javascript
// other code...

// TODO 8 : Do the reset steps //
txtUserInput.value = "";
doReset();

// other code...

```


# Other Resources

Continue your learning by visiting <a href="https://github.com/jfraboni/simple-node-app/wiki/Home" target="_blank">our JavaScript wiki</a>

And please visit <a href="http://operationspark.org" target="_blank">operationspark.org</a> to learn more about our project.


&copy; John Fraboni 2014