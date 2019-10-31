## == Please Note ==
This is a fork of the original repo of [cave][2]. I have updated the dependencies for it to be secure. I will also be slowly adding new features as I require them. The original seems to have been abandoned, so feel free to use this version in your projects.

Below is an updated readme file. You can find the original [here][3]

License: MIT

# cave
The main purpose of this module is to remove critical CSS from your stylesheet after inlining it in your pages. Once you have run your stylesheet through something like [penthouse][1] to extract critical css from a file, you are still left with the original file at the end. This module aims to extract those critical rules from the stylesheet so you only have the leftover css to lazyload in when required.

### Getting started
To install this updated version, run the following in your preferred Terminal:

```shell
npm install https://github.com/edwardjosephbennett/cave
```

*Want the original?*
You can install the original using:
```shell
npm install cave
```

### How it works

`cave` exposes a single function that takes the file path to a stylesheet and a string containing valid CSS you want to remove from the provided stylesheet.

Usage: `cave(stylesheet, options)`

Property        | Type | Description
----------------|------|--------------------------------------------------------------------------------------
`stylesheet`    | String | Provide a file path to the stylesheet you will be removing the rules from
`options`       | Object | Provide an object with options. 

See below table for available options to pass through as an object

Option          | Type | Description
----------------|------|--------------------------------------------------------------------------------------
`css`           | String | The CSS rules to remove from the stylesheet provided in string format. e.g: `a { color: #f00; }`
`compress`      | Boolean | Whether or not to compress output. *Available in this version only.*


Cave will produce an AST and remove any matching rules, then the resulting CSS diff will be returned.

### CLI

cave works well with standard input and is available for use on the command line. 

```shell
cat path/to/file | cave <stylesheet> > slim.css
```

You can also pass in the critical CSS file as an option.

```shell
cave --css path/to/file <stylesheet> > slim.css
```

### License

MIT

[1]: https://github.com/pocketjoso/penthouse
[2]: https://github.com/bevacqua/cave
[3]: README.ORIGINAL.md