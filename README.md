## == Please Note ==
This is a fork of the original repo of [cave][2]. I have updated the dependencies for it to be secure. I will also be slowly adding new features as I require them. The original seems to have been abandoned, so feel free to use this version in your projects.

License: MIT

# cave

> Remove critical CSS from your stylesheet after inlining it in your pages

If you don't understand the purpose of this module, refer to [penthouse][1] which extracts critical CSS from a file, but doesn't remove it. Using this tool you can take the styles produced by an extraction tool like [penthouse][1] and actually remove them from your stylesheet.

## Install

```shell
npm install cave --save
```

## API

The `cave` exposes a single function that takes the file path to a stylesheet and a string containing valid CSS you want to remove from the provided stylesheet.

### `cave(stylesheet, options)`

The `options` object contains the following properties.

Property | Description
---------|-----------------------------------------------------------------------
`css`    | The CSS rules to remove from the stylesheet. e.g: `a { color: #f00; }`

Cave will produce an AST and remove any matching rules, then the resulting CSS diff will be returned.

## CLI

Cave works well with standard input.

```shell
cat path/to/file | cave <stylesheet> > slim.css
```

You can also pass in the critical CSS file as an option.

```shell
cave --css path/to/file <stylesheet> > slim.css
```

## Tests

Run tests using `npm`.

```shell
npm test
```

## License

MIT

[1]: https://github.com/pocketjoso/penthouse
[2]: https://github.com/bevacqua/cave