# Sass Repository
This is the Scss Repository Where All The Basics of Sass are Covered.

<img src="https://caffeinecreations.ca/uploads/blog/_800x418_crop_center-center_82_none/sass-logo-new.png?mtime=1560450047" width="500px"/>

## Description
Description of the repository goes here.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Documentation](#documentation)
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

### Variables
#### Basic Variables
In SCSS, you can use variables to store and reuse values throughout your code. Variables are denoted by the '$' symbol followed by the variable name.

Syntax:
```scss
$primary-color: #007bff;
$font-size: 14px;
```

#### Variable Scope
Variables in SCSS have two scopes: global and local. Global variables are defined outside any selector or block and can be accessed from anywhere in the SCSS file. Local variables are defined inside a selector or a block and are only accessible within that scope.

Syntax:
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

#### Default Variables
You can assign default values to variables using the !default flag.

Syntax:
```scss
$button-color: #007bff !default;
$button-padding: 10px !default;
```

#### Variable Interpolation
Variable interpolation allows you to use variables within selectors or property names by wrapping them with #{}.

Syntax:
```scss
$theme: "dark";

.#{$theme}-background {
  background-color: black;
}

.#{$theme}-text {
  color: white;
}
```

### Mixins

#### Basic Mixins
Mixins are reusable blocks of code that can be included in multiple selectors.

Syntax:
```scss
@mixin border-radius($radius) {
  border-radius: $radius;
}

.button {
  @include border-radius(5px);
}
```

#### Parameterized Mixins
Mixins can take parameters, making them more flexible.

Syntax:
```scss
@mixin button-style($background-color, $text-color) {
  background-color: $background-color;
  color: $text-color;
}

.button {
  @include button-style(#007bff, #fff);
}
```

#### Mixin with Default Parameters
You can assign default values to mixin parameters using the !default flag.

Syntax:
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

#### Mixin with Variable Arguments
Sometimes you might need to pass a variable number of arguments to a mixin. You can use the ... notation to achieve this.

Syntax:
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

#### Mixin Guards
Mixin guards allow you to conditionally apply a mixin based on a certain condition. You can use the @if directive inside a mixin to achieve this.

Syntax:
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

### Inheritance

#### Extending Selectors
Inheritance allows you to share styles between selectors using the @extend directive. It helps keep your code DRY (Don't Repeat Yourself).

Syntax:
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

#### Placeholder Selectors
Placeholder selectors are

 similar to mixins but only generate CSS when extended using @extend. They are defined using % symbol.

Syntax:
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

#### Multiple Inheritance
You can extend multiple selectors or placeholder selectors using a comma-separated list.

Syntax:
```scss
.error {
  border: 1px solid red;
}

.message-box {
  @extend .error, %button-style;
  color: white;
}
```

### Functions

#### Built-in Functions
SCSS provides a set of built-in functions to perform various tasks, such as color manipulation, string operations, math calculations, etc.

Example:
```scss
$color: #007bff;

.darkened-color: darken($color, 10%);
```

#### Custom Functions
You can also create custom functions using the @function directive. Custom functions are useful when you want to encapsulate complex logic and reuse it.

Syntax:
```scss
@function divide($number, $divider) {
  @return $number / $divider;
}

.container {
  width: divide(1000px, 2);
}
```

### Control Directives

#### @if
The @if directive allows you to apply styles conditionally based on a given expression.

Syntax:
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

#### @for
The @for directive iterates over a range of values and generates styles accordingly.

Syntax:
```scss
@for $i from 1 through 3 {
  .item-#{$i} {
    width: 100px * $i;
  }
}
```

#### @each
The @each directive iterates over a list or a map and generates styles for each item.

Syntax:
```scss
$colors: red, green, blue;

@each $color in $colors {
  .box-#{$color} {
    background-color: $color;
  }
}
```

#### @while
The @while directive allows you to apply styles in a loop while a certain condition is true.

Syntax:
```scss
$i: 1;

@while $i < 5 {
  .item-#{$i} {
    opacity: 0.2 * $i;
  }
  $i: $i + 1;
}
```

### Modular SCSS Architecture

#### Folder Structure
A good SCSS project follows a modular architecture. Here's a sample folder structure:

Syntax:
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

#### Importing Partial Files
Use @import directive to import partial SCSS files into your main SCSS file.

Syntax:
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

#### Managing Dependencies
It's essential to manage the order of importing partial files to avoid conflicts. The general rule is to import files that define variables and mixins before using them.

### Best Practices

#### Code Organization
- Organize your code into smaller, reusable components.
- Use meaningful names for variables, mixins, and classes.
- Comment your code to explain complex logic or usage.

#### Naming Conventions
- Use lowercase letters and hyphens for class names (e.g., .main-container).
- Use underscores for variable and mixin names (e.g., $primary_color).
- Use CamelCase for function names (e.g., darkenColor()).

#### Performance Optimization
- Minimize the use of nested selectors to avoid generating overly specific CSS.
- Use placeholder selectors when you don't need styles to be generated unless extended.
- Avoid unnecessary mixin calls and keep your code DRY.

## Conclusion
Congratulations! You've learned the fundamentals of advanced SCSS development. By leveraging variables, mixins, inheritance, and functions, you can write modular, maintainable, and efficient SCSS code. Always follow best practices and keep your code organized for better collaboration and scalability. Happy coding!

## Contributing
If you want to contribute to this project or have found any issues, follow the guidelines below:

1. Fork the repository.
2. Create a new branch for your feature (git checkout -b feature-name).
3. Make the necessary changes and additions.
4. Commit your changes (git commit -m "Add feature-name").
5. Push to the branch (git push origin feature-name).
6. Open a Pull Request, and provide a detailed explanation of the changes made.

## License
This project is licensed under the MIT License.

Please let me know if you need further assistance or if there's anything else I can help you with!
