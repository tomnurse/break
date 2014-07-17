# break()
**Sass mixin for a shorthand SCSS breakpoint syntax**

This Sass mixing aims to combine the DRY nature of defining site-wide breakpoints as variables, with the ability to define one-time breakpoints – quickly – on the fly.

## Usage
For use with a Sass-based (SCSS) workflow, define quick breakpoints in the following easy ways:

- Passing a variable [string] for repeated use
- Passing a single min- or max-width
- Passing a range of widths
- Passing fallback values for browsers not supporting media queries

### Default configuration
By default, if units are not specified, pixels are used.
If max- or min- width is not chosen for a single-value breakpoint, max-width is used.
(Both of these options are configurable in the mixin)

### Using variables for repeated queries

**SCSS:**
```css
$break--large: "(min-width: 1179px)";

@include break($break--large) {
	background-color: #0ff;
}
```

**Output:**
```css
@media (min-width: 1179px) {
	background-color: #0ff;
}
```

### Declaring a single min- or max-width

**Parameters:** size, constraint (optional), units (optional) 

**Syntax:**
```css

//min-width: 600px (uses default units – pixels)
@include break(600, min) {
	background-color: #0ff;
}

//Shorthand syntax
//max-width 50em (uses default constraint – max-width)
@include break(50, em) {
	background-color: #0ff;
}

//min-width: 40rem
@include break(40, min, rem) {
	background-color: #0ff;
}

//max-width: 700px (uses default units and constraint)
@include break(700) {
	background-color: #0ff;
}
```

### Declaring both min- and max-width

**Parameters:** size, constraint (optional), size, constraint (optional), units (optional) 

**Syntax:**
```css

//min-width: 20em and max-width: 40em
@include break(20, min, 40, max, em) {
	background-color: #0ff;
}

//min-width: 500px and max-width: 600px (uses default units)
@include break(500, min, 600, max) {
	background-color: #0ff;
}

//Shorthand syntax
//min-width: 40em and max-width: 50em (uses automatic constraints)
@include break(40, 50, em) {
	background-color: #0ff;
}

//min-width: 400px and max-width: 700px (uses default units and automatic constraints)
@include break(400, 700) {
	background-color: #0ff;
}
```

### Outputting a non-media queried stylesheet
```css
@include break(none) {
	background-color: #0ff;
}
```
