# CSS / Sass Styleguide
Standards for developing flexible, durable, and sustainable CSS and Sass.

## CSS Rules
#### Use soft tabs (2 spaces) for indentation

#### Prefer dashes over camelCasing in class names.
```
/* Good */
.buttonPrimary {
  display: block; 
  padding: 10px 15px;
  outline: 0;
  background: #191919
}

.isActive {
  background: #4655a5;
}

/* Better */
.button-primary {
  display: block; 
  padding: 10px 15px;
  outline: 0;
  background: #191919
}

.is-active {
  background: #4655a5;
}
```

#### Do not use ID selectors
#### When grouping multiple selectors, keep individual selectors to a single line.

```
/* Good */
.primary, .section, .footer {
  display: block;
  padding: 10px 15px;
}

/* Better */
.primary,
.section,
.footer {
  display: block;
  padding: 10px 15px;
}
```

#### Include one space before the opening brace '{' in rule declarations
```
/* Good */
.primary{
  display: block;
}

/* Better */
.primary {
  display: block;
}
```

#### In properties, put a space after, but not before, the ':' character.
```
/* Bad */
.primary {
  display : block;
}

.main {
  display :block;
}
/* Good */
.primary {
  display: block;
}

.main {
  display: block;
}
```

#### Place closing braces '}' of rule declarations on a new line
```
/* Good */
.primary {
  display: block; }
  
/* Better */
.primary {
  display: block;
}
```

#### End all declarations with a semi-colon.

```
/* Good */
.button {
  display: block; 
  padding: 10px 15px;
  outline: 0;
  background: #191919
}

/* Better */
.button {
  display: block; 
  padding: 10px 15px;
  outline: 0;
  background: #191919;
}
```

#### Lowercase all hex values and use shorthand hex values where available.
```
/* Good */
.label {
  color: #FFFFFF;
}
/* Better */
.label {
  color: #fff;
}
```

#### Avoid specifying units for zero values
```
/* Good */
.link {
  margin: 0px;
}

/* Better */
.link {
  margin: 0;
}
```

#### Use shorthand notation for code efficiency
```
/* Good */
.button {
  margin-left: auto;  
  margin-right: auto;  
  padding-top: 10px;
  padding-bottom: 10px;
  padding-left: 15px;
  padding-right: 15px;
}


/* Better */
.button {
  margin: 0 auto;
  padding: 10px 15px;
}
```

#### Use JavaScript-specific classes to bind to, prefixed with '.js-'
```
<button class="button button-primary js-submit-to-signup">Submit</button>
```

---

## Sass Rules

#### Use the '.scss' syntax, never the original '.sass' syntax
#### Limit Sass nesting up to three (3) levels deep only for readability
```
.button {
  margin-left: auto;  
  margin-right: auto;  
  background-color: #191919;
  padding-left: 15px;
  padding-right: 15px;
  
  &-primary {
    background-color: #4655a5;
    
    &.is-active {
      background-color: darken(#4655a5, 5%);
    }  
    
    > .icon {
      color: #fff;    
    }  
  } // .button-primary
}
```

#### Make good use of available mixin libraries on the web [Compass](http://compass-style.org/) and [Bourbon](http://bourbon.io/)

#### Prefer dashes over camelCasing in declaring Sass variables.
```
/* Good */
$brandPrimary: #4655a5;
$brandSecondary: #ddd;
$brandDark: #000;
$fontSansSerif: 'Montserrat', sans-serif;
$fontSerif: 'Georgia', serif;

/* Better */
$brand-primary: #191919;
$brand-secondary: #ddd;
$brand-dark: #000;
$font-sans-serif: 'Montserrat', sans-serif;
$font-serif: 'Georgia', serif;
```

#### Group your '@include' and '@extend' at the end to make it easier to read the entire selector.
```
/* Good */
.link {
  @extend .button;  
  @include transition(color 0.5s ease);
  color: #4655a5;
}

/* Better */
.link {
  color: #4655a5;
  @extend .button;
  @include transition(color 0.5s ease);
}
```
