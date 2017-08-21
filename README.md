# Mixins for CSS3 Gradient Patterns

`sass-gradient-patterns` is a collection of
[Sass](http://sass-lang.com/) mixins that allow you to
easily customize the CSS3 gradient patterns found in
Lea Verou's [Patterns Gallery](http://lea.verou.me/css3patterns/),
Bennett Feely's `background-blend-mode` [pattern gallery](http://bennettfeely.com/gradients/)
and more.

Check out the [interactive tool][tool] for customizing (and animating!) these mixins

## How to use it
1. Install with [npm](https://www.npmjs.com/): `npm install sass-gradient-patterns --save`

    OR [Download _gradient_patterns.scss](https://raw.github.com/helixbass/sass-gradient-patterns/master/_gradient_patterns.scss) to your Sass project.

2. Import the partial in your Sass files: `@import 'gradient_patterns';`

3. Use any of the pattern mixins (see below for examples)

## Included patterns
[Here][sassdocs] is a list of
all of the included mixins (grouped by source gallery) and their keyword parameters.
All patterns from Lea Verou's and Bennett Feely's galleries are included.

## Customizing
All of the mixins accept keyword parameters
(listed [here][sassdocs] by mixin)
so that you can easily tweak 
individual aspects (eg colors, angles, sizes) of the pattern. Or just include the mixin
with no arguments for the default version of the pattern found in the original gallery.

The `$scale` parameter is accepted by most of the mixins to control the
overall repeating pattern size.

For example, let's look at the `diagonal-stripes` mixin (from Lea Verou's [pattern](http://lea.verou.me/css3patterns/#diagonal-stripes)).

To include the original pattern as-is, simply include the mixin:
```
@import 'gradient_patterns';

.selector {
  @include diagonal-stripes;
}
```
`diagonal-stripes` allows you to customize:
- either of the colors - `$background-color` defaults to `gray` and `$stripe-color` defaults to semi-transparent white `rgba(255, 255, 255, .5)`
- the `$angle` of the stripes (defaults to `45deg`)
- like most patterns, the `$scale` of the overall pattern (here, defaults to `70px`)
- the `$stripe-width` (defaults to `50%` - this is not a literal CSS percentage value, but rather a percentage relative to the `$scale`)

So to make the stripes more purplish and enlarged, we could instead do:
```
.selector {
  @include diagonal-stripes($background-color: mediumorchid, $scale: 100px);
}
```
Or if we want the stripes to go towards the bottom right and for the darker stripes to be thinner:
```
.selector {
  @include diagonal-stripes($angle: 135deg, $stripe-width: 70%);
}
```

Most of the mixins follow similar conventions.

<!-- Be sure to check out the interactive tool for easy customization and to play around with animating the patterns! -->

<!-- Example of relative defaults -->

## Help
If you have questions about how to use any of these mixins,
feel free to open a Github [issue](https://github.com/helixbass/sass-gradient-patterns/issues)

## Contributing
Got more patterns to contribute? Or want to add more parameters to an existing pattern?
Feel free to open a pull request on [Github](https://github.com/helixbass/sass-gradient-patterns).
Please try and follow the Sassdoc conventions if you can so that the [documentation][sassdocs]
and [interactive tool][tool] will update seamlessly.
Or just open an issue with a link to a pattern you think is cool and I'll see if I can
implement it.

## Compatibility
These patterns use CSS3 gradients (`linear-gradient()`, `radial-gradient()`, `repeating-linear-gradient()`, `repeating-radial-gradient()`)
so depend on browser support, see eg [caniuse](http://caniuse.com)

[sassdocs]: http://helixbass.net/sass_gradient_patterns_sassdoc/index.html
[tool]: http://helixbass.net/projects/gradients

## License
MIT
