# Button Alignment 

All of the buttons that trigger google analyics goals must be entered into squarespace as a custom code block.

There are 3 different versions depending on the alignment of the button

- Right Aligned
- Left Aligned
- Center Aligned

This is determined by the class of the `<div>` in which the button is contained.


### Right Button Example

```HTML
<!-- Right button -->
    <div class="sqs-block button-block sqs-block-button" data-block-type="53">
        <div class="sqs-block-content">
            <div class="sqs-block-button-container--right" data-animation-role="button" data-alignment="right" data-button-size="medium" >
                <a href=""  onclick="" class="sqs-block-button-element--medium sqs-block-button-element" data-initialized="true">TEXT GOES HERE</a>
            </div>
        </div>
    </div>
```
    
Notice the ```class="sqs-block-button-container--right" ``` and `data-alignment="right"` in the third `<div>` down. This is what determines the alignement of the buttons.

To change the type of button, simply change out the `class="sqs-block-button-container--BUTTON-POSITION"` and `data-alignment="BUTTON-POSITION"` properties.

The possible properties are

```
right
left
center
```

### Templates


###### Right button
```HTML
<!-- Right button -->
    <div class="sqs-block button-block sqs-block-button" data-block-type="53">
        <div class="sqs-block-content">
            <div class="sqs-block-button-container--right" data-animation-role="button" data-alignment="right" data-button-size="medium" >
                <a href=""  onclick="" class="sqs-block-button-element--medium sqs-block-button-element" data-initialized="true">TEXT GOES HERE</a>
            </div>
        </div>
    </div>
```
###### Left Button
```HTML
<!-- Left button -->
    <div class="sqs-block button-block sqs-block-button" data-block-type="53">
        <div class="sqs-block-content">
            <div class="sqs-block-button-container--left" data-animation-role="button" data-alignment="left" data-button-size="medium" >
                <a href="" onclick="" class="sqs-block-button-element--medium sqs-block-button-element" data-initialized="true">TEXT GOES HERE</a>
            </div>
        </div>
    </div>
```
###### Center Button
```HTML
<!-- Center button -->
    <div class="sqs-block button-block sqs-block-button" data-block-type="53">
        <div class="sqs-block-content">
            <div class="sqs-block-button-container--center" data-animation-role="button" data-alignment="center" data-button-size="medium" >
                <a href="" onclick="" class="sqs-block-button-element--medium sqs-block-button-element" data-initialized="true">TEXT GOES HERE</a>
            </div>
        </div>
    </div>
```




# Button Action

To get the button to actually do anything, we need to modify the properties contained within the `<a href>` element.

There are three properties we need to modify:
```HTML
href=""
```
this is where the url of the link goes. This could be the url to another page on the website or the url to a pdf or other document.
```HTML
onclick=""
```
This is where the action that is exectued when a user clicks the button goes. For our purpose this is where the relevent Google Analytics code goes. More on this below.
```HTML
TEXT GOES HERE
```
This is where you the text you want displayed on the button goes.

### Example for product info PDF

The below code is for a **center aligned button** that **links to a spec sheet pdf** with a **Google Analytics Goal code triggered onclick** and button text **Download Lift Product Information**

```HTML
   <!-- Center button -->
    <div class="sqs-block button-block sqs-block-button" data-block-type="53">
        <div class="sqs-block-content">
            <div class="sqs-block-button-container--center" data-animation-role="button" data-alignment="center" data-button-size="medium" >
                <a 
                    href="/s/Spotlight-Solar-Lift-spec-sheet-11-18-19.pdf" 
                    onclick=" ga('send', 'event',
                    { 
                        eventCategory: 'Sales Materials Downloads',
                        eventAction: 'click',
                        eventLabel: 'solar powered tree lift'
                    });" 
                    class="sqs-block-button-element--medium sqs-block-button-element" 
                    target="_blank"
                    >Download Lift Product Information
                </a>
            </div>
        </div>
    </div>
```

# Adding Google Analytics Goals

To make a button trigger a goal, we need to change the code in the `onclick=""` property.

```HTML
onclick=" ga('send', 'event',
                    { 
                        eventCategory: 'GOAL NAME GOES HERE',
                        eventAction: 'click',
                        eventLabel: 'OPTIONAL DESCRIPTION GOES HERE'
                    });" 
```

`eventCategory` is the name of the goal you want this button to trigger

`eventAction` is what you want to trigger this event, in our case a user clicking the button

`eventLabel` is an optional label you can add

Here is a guide that goes into further detail [UNDERSTANDING HOW TO USE GOOGLE ANALYTICS EVENT TRACKING](https://bigbangthemes.net/blog/understanding-how-to-use-google-analytics-event-tracking/)

### Example for solar powered tree lift spec sheet download

```HTML
<a 
                    href="/s/Spotlight-Solar-Lift-spec-sheet-11-18-19.pdf" 
                    onClick=" ga('send', 'event',
                    { 
                        eventCategory: 'Sales Materials Downloads',
                        eventAction: 'click',
                        eventLabel: 'solar powered tree lift'
                    });" 
                    class="sqs-block-button-element--medium sqs-block-button-element" 
                    target="_blank"
                    >Download Lift Product Information
                </a>
```
