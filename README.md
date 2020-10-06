# Custom file upload button

Customizing the input `type="file"` is a bit annoying because it comes with a button and an unchangeable text.

<input id="upload" type="file" accept="image/*">
<br />
<br />

With the `::file-selector-button` pseudo-selector you can edit the default button. It's still annoying because some CSS properties affect both the button and the text and some affect only the button 😒.

Another caveat is browser support. All major browsers except **Firefox** support the pseudo-selector.

You can read about the [::file-selector-button](https://developer.mozilla.org/en-US/docs/Web/CSS/::file-selector-button) for more details.

## How to customize the default upload button

We have our html input tag:

```html
<input id="upload" type="file" accept="image/*" />
```

to give us

<input id="upload" type="file" accept="image/*">
<br>
<br>

Then in our css:

```css
input::-webkit-file-upload-button {
  background-color: peru;
  border: none;
  border-radius: 4px;
  padding: 10px 20px;
  box-shadow: 0 2px 8px 1px #454545;
  cursor: pointer;
}
```

then we have:

<input id="demo" type="file" accept="image/*">

<style>
  #demo::-webkit-file-upload-button {
  background-color: peru;
  border: none;
  border-radius: 4px;
  padding: 10px 20px;
  box-shadow: 0 2px 8px 1px #454545;
  color: white;
  text-transform: uppercase;
  cursor: pointer;
}
</style>
<br>
<br>

**Note** that I used `-webkit-file-upload-button` instead of `file-selector-button`. `-webkit-file-upload-button` is for **Webkit/Blink** browsers like **Chrome** and **Opera**.

It's up to you if you wanna keep the "No file chosen" text. In this case, I don't wanna keep it. I'm not sure if it can be removed completely but adding `position: absolute;` puts the text behind the button.

<input id="final" type="file" accept="image/*">

<style>
#final::-webkit-file-upload-button {
  position: absolute;
  background-color: peru;
  border: none;
  border-radius: 4px;
  padding: 10px 20px;
  box-shadow: 0 2px 8px 1px #454545;
  cursor: pointer;
  color: white;
  text-transform: uppercase;
}
</style>
<br>
<br>
<br>

Yayyy!!! 🎉🎉🎉 Now we have our completely customized upload button.

Check out the [full code on codepen.io](https://codepen.io/gameshaker/pen/rNLBxZQ).
