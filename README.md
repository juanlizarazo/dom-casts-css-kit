# dom-casts-css-kit

Source code of the animation package used with the [Learn DOM manipulation with easy modern JavaScript][udemy-course] course on udemy.com

# How to use it

- You must have the [image sprite][css-sprites] in your machine, for this example you can use [this one][portal-image]
- Install the last version of the package using `npm i dom-casts-css-kit@latest`
- Import the package in the scss file where you want to add the classes dinamically, e.g.  `@import "~dom-casts-css-kit/portal"`
- Include the imported mixin in your scss file using `@include add-portal-frames("portal")` (we typed 'portal' but you can use any name)
- In your js file, you must create a function to iterate through the classes you just generated with the mixin, if you alraedy have the `portalElement` that function should look something like this:
```js
#animate() {
    let frame = 1;

    const animate = () => {
      this.#portalElement.classList.remove(`portal-${frame}`);

        if (frame === 12) {
            frame = 1;
        }

        frame = frame + 1;
        this.#portalElement.classList.add(`portal-${frame}`);
    };

    setInterval(animate, 100);
}
```

## LICENSE

MIT

[udemy-course]: https://www.udemy.com/course/learn-dom-manipulation-with-easy-modern-javascript/
[css-sprites]: https://css-tricks.com/css-sprites/
[portal-image]: https://raw.githubusercontent.com/juanlizarazo/dom-casts/master/04.%20Creating%20elements/end/src/assets/portal.png