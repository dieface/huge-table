# HugeTable

Table component to handle huge sets of data, based on Facebook's FixedDataTable.

## How to use it

```javascript
// data and schema should come from the API

var mountNode = document.getElementById('table-results');

var options = {
  height: 400,
  width: 600
};

React.render(<HugeTable data={data} schema={schema} options={options} />, mountNode);
```

More comprehensive example can be found inside the [examples](examples) directory.

## Table API

- **data** - Takes an array of data that should be displayed inside the table,
- **schema** - Takes an array of objects defining the name of particular fields to look for inside teh `data` array, and their type of data, which will tell the table which Cell type to use for displaying a particular column of data. Check `examples` directory for exemplary set of data and schema files.
- **options.height** - Height of the table component,
- **options.width** - Width of the table component,
- **options.mixedContentImage** - Function that can handle mixed content warnings for images being loaded inside the table. Function will be invoked with image URL, and allows developers to decide what do do when page is loaded for example with `https`, and image url has `http` protocol. Check `examples` directory for an example on how to use this.

## Commands

### Production build
```
npm run prepublish
```

Build the project in a production ready way.

## Releasing

- Commit changes to the repository on a separate branch,
- Bump version in package.json file, after you are done with your changes (remember about SemVer!),
- After you are done with your functionality, or if you think it is large enough, create a pull request with master branch to be peer reviewed,
- After changes are merged into master branch, checkout master branch, run tests one more time, and publish this package to npm repository.

## Changelog

### 4.0.0

**Breaking change**

- Adding new option to the main table called "mixedContentImage".

## Todo

- Add tests for `CellUtils`, `ListCell` and `HugeTable`
- Add JS doc
- Try custom validation function to test `data` attribute based on the given schema
- Use `shape` validation on cellData
- Create an `EmptyCell` for empty cells