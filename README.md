# Kirby 2 // Focus

With this plugin for [Kirby 2](http://getkirby.com) editors can add an individual focus point to any image. By using a special crop method developers can 

## Requirements

+ Kirby CMS, Version **2.3+**
+ GD Library

## Preview

![Screenshot](screenshot.png)

## Installation

If you are using the [Kirby CLI](https://github.com/getkirby/cli) you can install this plugin by running the following command in your shell:

```
kirby plugin:install flokosiol/kirby-focus
```

Otherwise you can download und unpack the zip file and put the `focus` folder into the `site/plugins` folder of your Kirby installation (create it, if it doesn't exist).

## Usage

Add the following line to your `config/config.php` file:

```
c::set('thumbs.driver', 'focus');
```

Add the focus field to file fields of your blueprint and make sure to name it `focus` like this:

```
files:
  fields: 
    focus: 
      label: My Focus field
      type: focus
```


Call the focusCrop method in your template:

```
<?php 

  // crop a square of 200px x 200px
  echo $image->focusCrop(200); 

  // crop a rectangle of 300px x 200px
  echo $image->focusCrop(300,200); 

  // crop a rectangle of 200px x 400px with a quality of 80%
  echo $image->focusCrop(200,400,80); 

?>
```

## Optional

You can change the key of the focus field by adding the following to your `config.php`:

```
c::set('focus.field.key', 'betterfocuskey');
```



