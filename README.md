# 🎯 Basic Theming in Angular Material 🎯

## 👋 Introduction
This repository is a step by step utilization of **Angular Theming** using mixins. The palettes was created based on Manulife's color branding.

> ✏️ Note
> The application is using **angular@14.2.13** and **angular/material@13.0.0**


## 📃 Procedures
- [ ] Create New Application in Angular
- [ ] Install and Setup Angular Material
- [ ] Download Palette provided or Create Your Own
- [ ] Implement Basic Theming

### 1. Create New Application in Angular
Create a new web application using Angular CLI
```
ng new ANGULAR-MATERIAL-BASIC-THEMING
```

### 2. Install and Setup Angular Material
To install angular material using Angular CLI:
```
ng add @angular/material
```
This will automatically detects which angular material your application is compatible with.

![Screenshot 2024-06-14 054556](https://github.com/labisda/angular-material-basic-theming/blob/master/src/assets/images/Screenshot%202024-06-14%20054556.png)



### 3. Download Palette provided or Create Your Own
To download/copy Manulife's palette.scss go (here)[https://github.com/labisda/angular-material-basic-theming/blob/master/src/assets/shared/_palette.scss] or you can also create your own using [Angular Palette Generator](http://mcg.mbitson.com/#!?mcgpalette0=%233f51b5)


### 4. Implement Basic Theming
Go to your style.scss

Import angular material and the pallete you created/copied then modify it based on the pallete.scss filepath. 
```
@use '@angular/material' as mat;
@use '/src/assets/shared/palette' as palette; 

@include mat.core();
```

Create basic theming
```
$angular-material-basic-theming-primary: mat.define-palette(palette.$greenCore, green5, green6, green7);
$angular-material-basic-theming-accent: mat.define-palette(palette.$coralAccent, coral5, coral6, coral7);

// The warn palette is optional (defaults to red).
$angular-material-basic-theming-warn: mat.define-palette(palette.$coralAccent, coral5, coral6, coral7);

// Create the theme object. A theme consists of configurations for individual
// theming systems such as "color" or "typography".
$angular-material-basic-theming-theme: mat.define-light-theme((
            color: (
                primary: $angular-material-basic-theming-primary,
                accent: $angular-material-basic-theming-accent,
                warn: $angular-material-basic-theming-warn,
            )
        ));

// Include theme styles for core and each component used in your app.
// Alternatively, you can import and @include the theme mixins for each component
// that you are using.
@include mat.all-component-themes($angular-material-basic-theming-theme);
```