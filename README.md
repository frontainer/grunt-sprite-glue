# grunt-sprite-glue
[![Build Status](https://travis-ci.org/frontainer/grunt-sprite-glue.svg)](https://travis-ci.org/frontainer/grunt-sprite-glue)
[![npm version](https://badge.fury.io/js/grunt-sprite-glue.svg)](http://badge.fury.io/js/grunt-sprite-glue)

Sprite generator with Glue & Grunt.  

## Getting Started
This plugin requires 

* [Grunt](http://gruntjs.com/) `~0.4.5`
* [Glue](http://glue.readthedocs.org/en/latest/) `0.9.4~`

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. 

Once you're familiar with that process, you may install this plugin with this command:

```js
grunt.loadNpmTasks('grunt-sprite-glue');
```

## The "spglue" task

### Overview
In your project's Gruntfile, add a section named `spglue` to the data object passed into `grunt.initConfig()`.

```js
grunt.initConfig({
  spglue: {
    options: {
      // Task-specific options go here.
    },
    your_target: {
      files: {
        '/path/to/': '/path/images/'
      }
      // Target-specific file lists and/or options go here.
    },
  },
});
```

### Options

#### options.algorithm
Type: `String`
Default value: `null`

The criteria that glue uses to order the images before adding them to the canvas can be tunned.  

* square
* vertical
* vertical-right
* horizontal
* horizontal-bottom
* dianomal


#### options.crop
Type: `Boolean`
Default value: `false`

Optimize our sprite by croping all the unnecessary transparent spaces that the original images could have.

#### options.caat
Type: `Boolean`
Default value: `false`

Generate both a sprite image and a caat metadata file.

#### options.cachebuster
Type: `Boolean`
Default value: `false`

Automatically add the hash of the PNG file to the CSS url

#### options.cachebusterFilename
Type: `String`
Default value: `null`

Insted of using the hash of the PNG as a queryarg it uses it as part of the filename.

#### options.cachebusterFilenameOnlySprites
Type: `Boolean`
Default value: `false`

Only apply filename cachebusting to the sprite image and not to both the CSS and the sprite image.

#### options.cocos2d
Type: `Boolean`
Default value: `false`

Generate both a sprite image and a xml metadata file compatible with cocos2d.

#### options.css
Type: `String`
Default value: `null`

Choose an individual folder for css  you. 

#### options.img
Type: `String`
Default value: `null`

Choose an individual folder for image. 

#### options.cssTemplate
Type: `String`
Default value: `null`

You can use your own css template

#### options.force
Type: `Boolean`
Default value: `false`

In order to avoid this behaviour you can use force and glue will always build the sprites.

#### options.followLinks
Type: `Boolean`
Default value: `false`

Follow symbolic links.

#### options.html
Type: `Boolean`
Default value: `false`

Generate a test html per sprite using all the available CSS classes. This option is only useful for testing purposes.

#### options.json
Type: `Boolean`
Default value: `false`

Generate both a sprite image and a json metadata file.

#### options.jsonFormat
Type: `String`
Default value: `null`

You can customize how the generated JSON will look. You can choose between array and hash.

#### options.less
Type: `Boolean`
Default value: `false`

Glue can also create .less files 

#### options.lessTemplate
Type: `String`
Default value: `null`

You can use your own less template

#### options.margin
Type: `Number`
Default value: `null`

If you want to spread the images around the sprite but you don’t want to count this space as image width/height.

#### options.namespace
Type: `String`
Default value: `null`

your own namespace you can override the default one.

#### options.noImg
Type: `Boolean`
Default value: `false`

Don’t create any sprite image.

#### options.noCss
Type: `Boolean`
Default value: `false`

Don’t create any CSS file.

#### options.ordering
Type: `String`
Default value: `null`

Before processing the images using the algorithm glue orders the images.

* maxside
* width
* height
* area
* filename

#### options.padding
Type: `Number`
Default value: `null`

If you want to add the same padding around all images.

#### options.png8
Type: `Boolean`
Default value: `false`

By using the flag png8 the output image format will be png8 instead of png32.

#### options.project
Type: `Boolean`
Default value: `false`

Generate several sprites for a project.

#### options.pseudoClassSeparator
Type: `String`
Default value: `null`

using the filename of the source images you can customize the pseudo class related to the images.

#### options.quiet
Type: `Boolean`
Default value: `false`

This flag will make glue suppress all console output.

#### options.recursive
Type: `Boolean`
Default value: `false`

Read directories recursively and add all the images to the same sprite.

#### options.ratios
Type: `String`
Default value: `null`

Automatically scale down your sprites to automatically fit them into low-dpi devices. 

#### options.retina
Type: `Boolean`
Default value: `false`

The option retina is only a shortcut for ratios=2,1.

#### options.source
Type: `String`
Default value: `null`

Source directory.

#### options.output
Type: `String`
Default value: `null`

Output directory.

#### options.scss
Type: `Boolean`
Default value: `false`

Glue can also create .scss files.

#### options.scssTemplate
Type: `String`
Default value: `null`

You can use your own scss template

#### options.separator
Type: `String`
Default value: `null`

Separator for the CSS class names. 

#### options.spriteNamespace
Type: `String`
Default value: `null`

Sprite’s name as past of the CSS class namespace.

#### options.url
Type: `String`
Default value: `null`

PNG file name the relative url between the CSS and the PNG file.

#### options.watch
Type: `Boolean`
Default value: `false`

While you are developing a site it could be quite frustrating running Glue.

### Usage Examples
	spglue: {
            options: {
            },
            dev: {
                options: {
                    project: true,
                    scss: true
                },
                files: {
                    'css/sass': 'images/sprites'
                }
            }
        }


## Release History
_(Nothing yet)_
