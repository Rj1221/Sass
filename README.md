# Sass
This is the Scss Repository Where All The Basics of Sass is Covered
<img src="https://caffeinecreations.ca/uploads/blog/_800x418_crop_center-center_82_none/sass-logo-new.png?mtime=1560450047" alt="Sass Image" width="550px"/>
# Repository Name
Sass
# Description 
Description of the repository goes here.

- [Installation](#installation)
- [Usage](#usage)
- [Documentation](#documentation)
- [Modular SCSS Architecture](#modular-scss-architecture)
- [Best Practices](#best-practices)
- [Contributing](#contributing)
- [License](#license)

## Installation

Provide step-by-step instructions on how to set up and use the SCSS code in this repository. Include any prerequisites and installation requirements.

```bash
# Step 1: Clone the repository
git clone https://github.com/your-username/repository-name.git

# Step 2: Navigate to the project folder
cd repository-name

# Step 3: Install dependencies (if any)
npm install

# Step 4: Compile SCSS to CSS
sass main.scss main.css

# Step 5: (Optional) Watch for changes and automatically compile
sass --watch main.scss:main.css
```

## Usage

Explain how to use the SCSS code provided in this repository. Include any relevant details about the project structure, files, and how to make customizations.


### Example Usage

```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <!-- Your HTML content here -->
</body>
</html>
```
## Documentation
# Advanced SCSS Developer Documentation

## Table of Contents

- [Introduction](#introduction)
- [Variables](#variables)
  - [Basic Variables](#basic-variables)
  - [Variable Scope](#variable-scope)
  - [Default Variables](#default-variables)
  - [Variable Interpolation](#variable-interpolation)
- [Mixins](#mixins)
  - [Basic Mixins](#basic-mixins)
  - [Parameterized Mixins](#parameterized-mixins)
  - [Mixin with Default Parameters](#mixin-with-default-parameters)
  - [Mixin with Variable Arguments](#mixin-with-variable-arguments)
  - [Mixin Guards](#mixin-guards)
- [Inheritance](#inheritance)
  - [Extending Selectors](#extending-selectors)
  - [Placeholder Selectors](#placeholder-selectors)
  - [Multiple Inheritance](#multiple-inheritance)
- [Functions](#functions)
  - [Built-in Functions](#built-in-functions)
  - [Custom Functions](#custom-functions)
- [Control Directives](#control-directives)
  - [@if](#if)
  - [@for](#for)
  - [@each](#each)
  - [@while](#while)
- [Modular SCSS Architecture](#modular-scss-architecture)
  - [Folder Structure](#folder-structure)
  - [Importing Partial Files](#importing-partial-files)
  - [Managing Dependencies](#managing-dependencies)
- [Best Practices](#best-practices)
  - [Code Organization](#code-organization)
  - [Naming Conventions](#naming-conventions)
  - [Performance Optimization](#performance-optimization)
- [Conclusion](#conclusion)


## 1. Introduction

Welcome to the Advanced SCSS Developer Documentation! This guide aims to help you become proficient in writing scalable, maintainable, and efficient SCSS code. SCSS (Sassy CSS) is an extension of CSS that introduces powerful features such as variables, mixins, inheritance, and more.

## 2. Variables

### 2.1. Basic Variables

In SCSS, you can use variables to store and reuse values throughout your code. Variables are denoted by the '$' symbol followed by the variable name.

### 2.2. Variable Scope

Variables in SCSS have two scopes: global and local.

### 2.3. Default Variables

You can assign default values to variables using the !default flag.

### 2.4. Variable Interpolation

Variable interpolation allows you to use variables within selectors or property names by wrapping them with #{}.

## 3. Mixins

### 3.1. Basic Mixins

Mixins are reusable blocks of code that can be included in multiple selectors.

### 3.2. Parameterized Mixins

Mixins can take parameters, making them more flexible.

### 3.3. Mixin with Default Parameters

You can assign default values to mixin parameters using the !default flag.

### 3.4. Mixin with Variable Arguments

Sometimes you might need to pass a variable number of arguments to a mixin.

### 3.5. Mixin Guards

Mixin guards allow you to conditionally apply a mixin based on a certain condition.

## 4. Inheritance

### 4.1. Extending Selectors

Inheritance allows you to share styles between selectors using the @extend directive.

### 4.2. Placeholder Selectors

Placeholder selectors are similar to mixins but only generate CSS when extended using @extend.

### 4.3. Multiple Inheritance

You can extend multiple selectors or placeholder selectors using a comma-separated list.

## 5. Functions

### 5.1. Built-in Functions

SCSS provides a set of built-in functions to perform various tasks.

### 5.2. Custom Functions

You can create custom functions using the @function directive.

## 6. Control Directives

### 6.1. @if

The @if directive allows you to apply styles conditionally based on a given expression.

### 6.2. @for

The @for directive iterates over a range of values and generates styles accordingly.

### 6.3. @each

The @each directive iterates over a list or a map and generates styles for each item.

### 6.4. @while

The @while directive allows you to apply styles in a loop while a certain condition is true.

## 7. Modular SCSS Architecture

### 7.1. Folder Structure

A good SCSS project follows a modular architecture. Here's a sample folder structure:

### 7.2. Importing Partial Files

Use @import directive to import partial SCSS files into your main SCSS file.

### 7.3. Managing Dependencies

It's essential to manage the order of importing partial files to avoid conflicts.

## 8. Best Practices

### 8.1. Code Organization

Organize your code into smaller, reusable components.

### 8.2. Naming Conventions

Use meaningful names for variables, mixins, and classes.

### 8.3. Performance Optimization

Minimize the use of nested selectors and avoid unnecessary mixin calls.

## 9. Conclusion

Congratulations! You've learned the fundamentals of advanced SCSS development. By leveraging variables, mixins, inheritance, and functions, you can write modular, maintainable, and efficient SCSS code. Always follow best practices and keep your code organized for better collaboration and scalability. Happy coding!


## 1. Introduction

Welcome to the Advanced SCSS Developer Documentation! This guide aims to help you become proficient in writing scalable, maintainable, and efficient SCSS code. SCSS (Sassy CSS) is an extension of CSS that introduces powerful features such as variables, mixins, inheritance, and more.

To use SCSS, you need to have a preprocessor that compiles it into standard CSS. Popular preprocessor options include Sass and Node-sass.

## 2. Variables

### 2.1. Basic Variables

In SCSS, you can use variables to store and reuse values throughout your code. Variables are denoted by the '$' symbol followed by the variable name. Here's an example:

```scss
$primary-color: #007bff;
$font-size: 14px;

body {
  color: $primary-color;
  font-size: $font-size;
}
```

### 2.2. Variable Scope

Variables in SCSS have two scopes: global and local. Global variables are defined outside any selector or block and can be accessed from anywhere in the SCSS file. Local variables are defined inside a selector or a block and are only accessible within that scope.

```scss
$global-var: red;

.parent {
  $local-var: blue;
  color: $local-var; // Accessible only within .parent
}

.child {
  color: $global-var; // Accessible everywhere
}
```

### 2.3. Default Variables

You can assign default values to variables using the `!default` flag. If the variable is already defined, the default value will be ignored.

```scss
$button-color: #007bff !default;
$button-padding: 10px !default;

.button {
  background-color: $button-color;
  padding: $button-padding;
}
```

### 2.4. Variable Interpolation

Variable interpolation allows you to use variables within selectors or property names by wrapping them with `#{}`.

```scss
$theme: "dark";

.#{$theme}-background {
  background-color: black;
}

.#{$theme}-text {
  color: white;
}
```
### Multiple Value Declaration and using  map-get()
```scss
// Define a map with multiple values
$theme-colors: (
  primary: #007bff,
  secondary: #dc3545,
  success: #28a745,
  warning: #ffc107,
  danger: #dc3545
);

// Retrieve values from the map using the map-get() function
body {
  color: map-get($theme-colors, primary);
  background-color: map-get($theme-colors, secondary);
}

.button {
  background-color: map-get($theme-colors, danger);
  border: 1px solid map-get($theme-colors, warning);
}
```

## 3. Mixins

### 3.1. Basic Mixins

Mixins are reusable blocks of code that can be included in multiple selectors. They are denoted by the `@mixin` directive and included using `@include`.

```scss
@mixin border-radius($radius) {
  border-radius: $radius;
}

.button {
  @include border-radius(5px);
}
```

### 3.2. Parameterized Mixins

Mixins can take parameters, making them more flexible. Parameters are declared inside parentheses after the mixin name.

```scss
@mixin button-style($background-color, $text-color) {
  background-color: $background-color;
  color: $text-color;
}

.button {
  @include button-style(#007bff, #fff);
}
```

### 3.3. Mixin with Default Parameters

You can assign default values to mixin parameters using the same `!default` flag we used for variables.

```scss
@mixin button-style($background-color: #007bff, $text-color: #fff) {
  background-color: $background-color;
  color: $text-color;
}

.button {
  @include button-style; // Uses default values
}

.primary-button {
  @include button-style(#dc3545, #fff); // Overrides default values
}
```

### 3.4. Mixin with Variable Arguments

Sometimes you might need to pass a variable number of arguments to a mixin. You can use the `...` notation to achieve this.

```scss
@mixin box-shadow($shadows...) {
  box-shadow: $shadows;
}

.card {
  @include box-shadow(0 0 5px rgba(0, 0, 0, 0.1));
}

.button {
  @include box-shadow(2px 2px 4px rgba(0, 0, 0, 0.2), 0 0 1px rgba(0, 0, 0, 0.1));
}
```

### 3.5. Mixin Guards

Mixin guards allow you to conditionally apply a mixin based on a certain condition. You can use the `@if` directive inside a mixin to achieve this.

```scss
@mixin no-text-select() {
  @if (not $allow-text-select) {
    user-select: none;
  }
}

.button {
  @include no-text-select; // Applies the mixin if $allow-text-select is false
}
```

## 4. Inheritance

### 4.1. Extending Selectors

Inheritance allows you to share styles between selectors using the `@extend` directive. It helps keep your code DRY (Don't Repeat Yourself).

```scss
.button {
  padding: 10px;
  background-color: #007bff;
}

.submit-button {
  @extend .button; // Inherits styles from .button
  color: white;
}
```

### 4.2. Placeholder Selectors

Placeholder selectors are similar to mixins but only generate CSS when extended using `@extend`. They are defined using `%` symbol.

```scss
%button-style {
  padding: 10px;
  background-color: #007bff;
}

.button {
  @extend %button-style;
  color: white;
}

.another-button {
  @extend %button-style;
  color: black;
}
```

### 4.3. Multiple Inheritance

You can extend multiple selectors or placeholder selectors using a comma-separated list.

```scss
.error {
  border: 1px solid red;
}

.message-box {
  @extend .error, %button-style;
  color: white;
}
```

## 5. Functions

### 5.1. Built-in Functions

SCSS provides a set of built-in functions to perform various tasks, such as color manipulation, string operations, math calculations

, etc.

```scss
$color: #007bff;

.darkened-color: darken($color, 10%);
```

### 5.2. Custom Functions

You can also create custom functions using the `@function` directive. Custom functions are useful when you want to encapsulate complex logic and reuse it.

```scss
@function divide($number, $divider) {
  @return $number / $divider;
}

.container {
  width: divide(1000px, 2);
}
```

## 6. Control Directives

### 6.1. @if

The `@if` directive allows you to apply styles conditionally based on a given expression.

```scss
$background: "dark";

body {
  @if $background == "dark" {
    background-color: black;
    color: white;
  } @else {
    background-color: white;
    color: black;
  }
}
```

### 6.2. @for

The `@for` directive iterates over a range of values and generates styles accordingly.

```scss
@for $i from 1 through 3 {
  .item-#{$i} {
    width: 100px * $i;
  }
}
```

### 6.3. @each

The `@each` directive iterates over a list or a map and generates styles for each item.

```scss
$colors: red, green, blue;

@each $color in $colors {
  .box-#{$color} {
    background-color: $color;
  }
}
```

### 6.4. @while

The `@while` directive allows you to apply styles in a loop while a certain condition is true.

```scss
$i: 1;

@while $i < 5 {
  .item-#{$i} {
    opacity: 0.2 * $i;
  }
  $i: $i + 1;
}
```

## 7. Modular SCSS Architecture

### 7.1. Folder Structure

A good SCSS project follows a modular architecture. Here's a sample folder structure:

```
styles/
  |- base/
  |   |- _variables.scss
  |   |- _mixins.scss
  |   |- _functions.scss
  |
  |- components/
  |   |- _buttons.scss
  |   |- _cards.scss
  |   |- _modals.scss
  |
  |- layout/
  |   |- _header.scss
  |   |- _footer.scss
  |
  |- main.scss
```

### 7.2. Importing Partial Files

Use `@import` directive to import partial SCSS files into your main SCSS file.

```scss
// main.scss

@import 'base/variables';
@import 'base/mixins';
@import 'base/functions';

@import 'components/buttons';
@import 'components/cards';
@import 'components/modals';

@import 'layout/header';
@import 'layout/footer';
```

### 7.3. Managing Dependencies

It's essential to manage the order of importing partial files to avoid conflicts. The general rule is to import files that define variables and mixins before using them.

## 8. Best Practices

### 8.1. Code Organization

- Organize your code into smaller, reusable components.
- Use meaningful names for variables, mixins, and classes.
- Comment your code to explain complex logic or usage.

### 8.2. Naming Conventions

- Use lowercase letters and hyphens for class names (e.g., `.main-container`).
- Use underscores for variable and mixin names (e.g., `$primary_color`).
- Use CamelCase for function names (e.g., `darkenColor()`).

### 8.3. Performance Optimization

- Minimize the use of nested selectors to avoid generating overly specific CSS.
- Use placeholder selectors when you don't need styles to be generated unless extended.
- Avoid unnecessary mixin calls and keep your code DRY.

## 9. Conclusion

Congratulations! You've learned the fundamentals of advanced SCSS development. By leveraging variables, mixins, inheritance, and functions, you can write modular, maintainable, and efficient SCSS code. Always follow best practices and keep your code organized for better collaboration and scalability. Happy coding!

## Contributing

If you want to contribute to this project or have found any issues, follow the guidelines below:

1. Fork the repository.
2. Create a new branch for your feature (`git checkout -b feature-name`).
3. Make the necessary changes and additions.
4. Commit your changes (`git commit -m "Add feature-name"`).
5. Push to the branch (`git push origin feature-name`).
6. Open a Pull Request, and provide a detailed explanation of the changes made.

## License

This project is licensed under the [MIT License](LICENSE).
