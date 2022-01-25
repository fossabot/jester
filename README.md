# jester

[![Git](https://app.soluble.cloud/api/v1/public/badges/3c256f3e-070c-4520-bc99-d864b832fa68.svg?orgId=320408544746)](https://app.soluble.cloud/repos/details/github.com/jsoehner/jester?orgId=320408544746)  
[![CircleCI Status](https://circleci.com/gh/scotiabank/jester.svg?style=shield&circle-token=:circle-token)](https://circleci.com/gh/scotiabank/jester)

Jester DRYs up your Jest + React snapshot code.

## Why use jester?

Jester React will reduce the amount of boilerplate you write significantly.

Example without jester:

```js
import { Header, Paragraph } from './components';
import { shallow } from 'enzyme';
import toJSON from 'enzyme-to-json';

describe('components', () => {
  test('header should match snapshot', () => {
    const tree = toJson(shallow(<Header />));
    expect(tree).toMatchSnapshot();
  });
  test('paragraph should match snapshot', () => {
    const tree = toJson(shallow(<Paragraph />));
    expect(tree).toMatchSnapshot();
  });
});
```
Example with jester:

```js
import * as Components from './components';
import jester from '@scotia/jester-react';

describe('shallow', () => {
  jester.runShallowSnapshotTests(Components);
});
```

As you can see for each component that is added the more boilerplate code jester saves you (about 4 lines per component).


## Packages

This repository is a monorepo that we manage using [Lerna](https://github.com/lerna/lerna). That means that we actually publish [multiple packages](/packages) to npm from the same codebase, including:

| Package | Version | Description |
|---------|---------|-------------|
| [`jester`](/packages/jester) | [![npm](https://img.shields.io/npm/v/@scotia/jester.svg?style=flat-square)](https://www.npmjs.com/package/@scotia/jester) | The basic version for creating snapshots with plain JSON |
| [`jester-react`](/packages/jester-react) |[![npm](https://img.shields.io/npm/v/@scotia/jester-react.svg?style=flat-square)](https://www.npmjs.com/package/@scotia/jester-react) | The React specific version for use with React Components|

## Contributing

#### Scotiabank is committed to enriching the developer community through open source collaboration. We’ve just begun this exciting journey with all of you! At present, we’re only accepting contributions from individuals with whom we have a prior agreement. Stay tuned for more updates from us!
