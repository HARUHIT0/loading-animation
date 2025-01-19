# Loading Animation on Hover

## Table of Contents

- [Introduction](#introduction)
- [Project Structure](#project-structure)
- [Step-by-Step Guide](#step-by-step-guide)
  - [1. Create the HTML File](#1-create-the-html-file)
  - [2. Create the CSS File](#2-create-the-css-file)
  - [3. Link the CSS](#3-link-the-css)
  - [4. Adding the div classes](#4-adding-the-div-classes)
  - [5. Calling the div classes](#5-calling-the-div-classes)
  - [6. Container](#6-container)
  - [7. Creating the object for the animation](#7-creating-the-object-for-the-animation)
  - [8. Positioning the object](#8-positioning-the-object)
  - [9. Animating the object](#9-animating-the-object)
  - [10. Open the HTML File in a Browser](#10-open-the-html-file-in-a-browser)
- [Things to Look Out For](#things-to-look-out-for)
- [Stretch Goals](#stretch-goals)
- [Conclusion](#conclusion)

## Introduction

In this tutorial, you'll learn how to create a loading animation when your cursor is hovering over the object. We will not be using JavaScript in this project.

## Project Structure

Create a project directory and set up the following file structure:
```plaintext
simple-website/
├── index.html
├── styles.css
```

## Step-by-Step Guide

### 1. Create the HTML File

Open your code editor and create a file named `index.html`. Add the following code:

```html
!DOCTYPE html>
<html>
<head>
    <title>On Hover Spinner</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    
</body>
</html>
```
### 2. Create the CSS File

Create a file named `styles.css` and add the following code to style your webpage:

```css
body {
  
}
```

## Part 1: HTML
 
### 3. Link the CSS

Ensure that the CSS and JavaScript files are linked correctly in your `index.html` file. The `<link>` tag for CSS should be inside the `<head>` section, and the `<script>` tag for JavaScript should be just before the closing `</body>` tag.

### 4. Adding the div classes

In `index.html` create a div tag with a class and name it `container`. Inside that div tag create 1 div tag under the `container`, name the div tag `crc1`. Inside that div tag create 1 div tag under the `crc1`, name the div tag `crc`. Now inside the div tag `crc`, repeat that process 10 more times.

Your code should look something like this.

<details>
  <summary>HTML Solution</summary>

  ```html
<!DOCTYPE html>
<html>
<head>
    <title>On Hover Spinner</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <div class="crc1">
            <div class="crc">
                <div class="crc">
                    <div class="crc">
                        <div class="crc">
                            <div class="crc">
                                <div class="crc">
                                    <div class="crc">
                                        <div class="crc">
                                            <div class="crc">
                                                <div class="crc">
                                                    <div class="crc">
                                                        
                                                    </div>
                                                </div>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</body>
</html>
```
</details>

## Part 2: CSS

### 5. Calling the div classes

Now that you created the div classes we can use those to create the animations. You can call the div class from `index.html` by typing a period following it with the name of the div class. For example, if I want to call the container, I would type `.container`. Any code that I would type under `.container` would only affect `.container`. We will need to call the other div classes such as `.crc1` and `crc`, but let's not worry about that for now and focus on one thing at a time.

### 6. Container

We will be using the "container" to contain the object for the animation.

- To make the container, we must enter the following under the container div class.
  - Set the height to 450px
  - Set the width to 450px
  - Set the background-color to black
  - Set the position to absolute
  - Set the margin to auto
  - Set "top" to 0
  - Set "bottom" to 0
  - Set "left" to 0
  - Set "right" to 0
 
<details>
  <summary>Container Solution</summary>

  ```css
  .container {
    height: 450px;
    width: 450px;
    background-color: black;
    position: absolute;
    margin: auto;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
}
  ```
</details>

### 7. Creating the object for the animation

Now that we have a container, we can now create our object. To make things more efficient, we can call both `crc1` and `crc` by adding a comma between them. That way, the code that we enter will apply to both of them.

It should look something like this.

<details>
  <summary>Example</summary>

  ```css
  .crc1, .crc {

}
  ```
</details>

Now that we called both `crc1` and `crc`, we can now create the object.

- To make the object, we must enter the following under the `.crc1, .crc` div class.
  - Set the height to 400px
  - Set the width to 70px
  - Set the border to 3px, solid, and the color to white
  - Set the position to relative
  - Set the border-radius to 50%
  - Set the transition to 2.5s linear
 
It should look something like this.

<details>
  <summary>Object Solution</summary>

  ```css
  .crc1, .crc {
    height: 400px;
    width: 70px;
    border: 3px solid rgb(255, 255, 255);
    position: relative;
    border-radius: 50%;
    transition: 2.5s linear;
}
```
</details>

### 8. Positioning the object

After creating the object, you will probably notice that the object isn't merged with each other. Let's fix that.

- To merge the object into one object, we have to call the div tags `.crc1` and `.crc`, but this time we have to enter them separately.
  -  In the `.crc1` we have to set `top` to 25px and `left` to 190px.
  -  In the `.crc` we have to set `bottom` and `right` 2.5px.

Your code should look something like this.

<details>
  <summary>Positioning Solution</summary>

  ```css
  .crc1 {
    top: 25px;
    left: 190px;
}

.crc {
    bottom: 2.5px;
    right: 2.5px;
}
  ```
</details>

### 9. Animating the object

Now that the object is merged, we can now animate the object. We will be using hover to trigger the animation.

- To animate the object we will need to call the div class `.crc1`, but this time we need to add `hover` to the class
  - An example of this would be `(insert div class):hover {}`
- Under the div class we need to set the animation to spin for 8 sec infinitely in a linear forward direction and also set a cursor pointer.

For the animation to truly work we need to have the object transform by rotating 15 degrees.

- To start it off, we need to call both `.crc1` and `crc`, but we need to have `hover` between the two of them.
- Under the div class we need to transform by rotating 15deg

Perfect, now it's missing one last piece of code. That code is called `@keyframes`, it controls the intermediate steps in a CSS animation sequence by defining styles for keyframes (or waypoints) along the animation sequence. This gives more control over the intermediate steps of the animation sequence than transitions.

- You can start it off by typing `@keyframes` and spin
- Under `@keyframe` we need to type 100%{}
  - Inside the {}, we need to type transform: rotate(360deg);

Your code should look something like this.

<details>
  <summary>Animating Solution</summary>

  ```css
  .crc1:hover {
    animation: spin 8s infinite linear forwards;
    cursor: pointer;
}

.crc1:hover .crc{
    transform: rotate(15deg);
}

@keyframes spin {
    100%{
        transform: rotate(360deg);
    }
}
  ```
</details>

### 10. Open the HTML File in a Browser

Open your `index.html` file in a web browser to see your simple website in action.

## Things to Look Out For

- Ensure the file paths in the `<link>` and `<script>` tags are correct.
- Use proper HTML structure and semantics.
- Keep your CSS organized and use meaningful class names.
- Test your website in different browsers to ensure compatibility.
- The positioning of the object may differ depending on the laptop/desktop size.

## Stretch Goals
If you finish early, feel free to make changes with the color and the shape of the object

## Conclusion

Congratulations! You've created a loading animation using HTML and CSS. This is just the beginning – there are many more features and technologies to explore. Keep learning and experimenting to build more complex and dynamic websites.

Feel free to reach out if you have any questions or feedback. Happy coding!