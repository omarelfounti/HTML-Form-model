# In-Pair-Programming

We will develop a simple web form that contains some validation styling. Our aim will be to produce a web form like the one shown in the screeshot.

- First, start by creating a new file called validation-form.html, and use the following snippet as a starting point:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Validation form</title>
    <style>
      body {
        font-family: arial, sans-serif;
      }
    </style>
  </head>
  <body>
    <form action="#" method="post">
      <fieldset>
        <!-- your code will go here -->
      </fieldset>
    </form>
  </body>
</html>
```

- We will now add the HTML for the first name and last name form fields between the opening and closing fieldset tags. Notice how we have added required attributes to both of the input elements:

```html

        <div>
          <label for="first_name">First name:</label><br />

          <input
            type="text"
            name="firstname"
            id="first_name"
            placeholder="Your first name"
            required
          />
        </div>

        <div>
          <label for="last_name">Last name:</label><br />

          <input
            type="text"
            name="lastname"
            id="last_name"
            placeholder="Your last name"
            required
          />
        </div>

```

Add the HTML for the remaining form elements. Notice that it is only the textarea element where we require the required attribute.

```html

        <label for="country">Country:</label>
        <div class="select-wrapper">
          <select id="country">
            <option value="finland">Finland</option>
            <option value="sweden">Sweden</option>
            <option value="india">India</option>
            <option value="canada">Canada</option>
          </select>
        </div>
          
        <label for="message">Message:</label><br/>
        <textarea id="message" rows="5" cols="20" placeholder="Your message" required></textarea>
        <br/><br/>

        <button type="submit">Submit</button>
```

- Now we will turn to the CSS. We will first add some styling, which will deal with spacing the div and fieldset elements:

```css
	
      div {
        margin-bottom: 30px;
      }

      fieldset {
        border: 0;
        padding: 30px;
      }
```

- Next, we will style the individual form elements one by one. The label's font size is set to 20px and the styling for the input and textarea elements is same as shown in the following code snippet:

```css

      label {
        font-size: 20px;
      }

      input,
      textarea {
        border: 0;
        border-bottom: 1px solid gray;
        padding: 10px 0;
        width: 200px;
      }

```

- With respect to the expected output as shown in the screenshot, we style select as shown in the following code snippet:

```css
      select {
        background: transparent;
        border: 0;
        border-radius: 0;
        border-bottom: 1px solid gray;
        box-shadow: none;
        color: #666;
        padding: 10px 0;
        width: 200px;
      }

```

- We will use the following snippet of code to complete styling the select:

```css

      .select-wrapper {
        position: relative;

        width: 200px;
      }

      .select-wrapper:after {
        content: "<>";
        color: #666;
        font-size: 14px;
        top: 8px;
        right: 0;
        transform: rotate(90deg);
        position: absolute;
        z-index: -1;
      }

```

- To style the button, we will use the the following code:

```css

      button {
        background: #999;
        border: 0;
        color: white;
        font-size: 12px;
        height: 50px;
        width: 200px;
        text-transform: uppercase;
      }
```

- We will add the styles to validate the form elements that have a required attribute:

```css

      input:valid,
      textarea:valid {
        border-bottom-color: green;
      }

      input:invalid,
      textarea:invalid {
        border-bottom-color: red;
      }
```

- Finally move the CSS to a separate file `styles.css`. Hint use Emmet's shortcut: `link`
> If You wondered why this is not the first step, then you are absolutely correct!
