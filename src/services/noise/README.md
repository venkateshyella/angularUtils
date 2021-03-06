# 1D Noise Generator

This is a simple implementation of a 1-dimensional interpolated noise generator. I adapted the example in [this excellent article](http://www.scratchapixel.com/lessons/3d-advanced-lessons/noise-part-1/creating-a-simple-1d-noise/)
(which is well worth studying for a easy-to-follow explanation of the concept from basic principles).

Noise functions are very useful when modelling unpredictability in nature - undulating terrain, movement of objects and (in more complex implementations) natural textures. A 1D noise function, such as this one, takes a numeric input and returns a corresponding value between 0 and 1. Think of it as similar to
the random numbers generated by the JavaScript `Math.random()` function, but smoothly transitioning from one value to the next (this is "interpolation"), rather than just jumping all over the place. That, in essence, is exactly
what this class does.

The service is simply a wrapper around a JavaScript object which allows it to be injected into an Angular app. It can be easily used in any non-Angular app just by using the object itself, and pulling it out of the
Angular `.factory()` wrapper.

## Demo

[http://plnkr.co/edit/u4uIjX5V698tI5CkBNPc?p=preview](http://plnkr.co/edit/u4uIjX5V698tI5CkBNPc?p=preview)

## Usage

In your Angular app, include the service by usual Angular dependency injection, then you can use it like this:

```JavaScript
var generator = noise.newGenerator();

var x = 1; // can be any number
var y = generator.getVal(x); // number between 0 and 1, e.g. 0.231144
```

You can generate a continuously varying sequence like this:

```JavaScript
var generator = noise.newGenerator();
 for (var i = 0; i < 200; i ++) {
    console.log(generator.getVal(i);
}
```

## Options

You can optionally set two properties via these methods:

- `setAmplitude(number)` : Alter the range between which the generated values will fall, e.g. setting it to 2 will generate values between 0 and 2. Default is 1.
- `setScale(number)` : Change the frequency of the function. A larger number "squashes" the values closer together, and vice-versa. When using the generator for animations (as in the second demo), this parameter can be thought of a "frequency". Default is 1.





Hello