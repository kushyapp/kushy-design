<p align="center">
  <a href="http://ant.design">
    <img width="230" src="https://kushy-frontend-assets.s3.amazonaws.com/assets/kushy-logo-short-red.svg">
  </a>
</p>

# Kushy Design

A human-centered design framework and UI system based on [Semantic UI](https://semantic-ui.com/).

## Getting Started

1. `npm install kushy-design && semantic-ui-react --save`

> You can [find this package on NPM here](https://www.npmjs.com/package/kushy-design)

### Using CSS

1. Import the master CSS file: `import 'kushy-design/semantic/dist/semantic.css'`
1. Or import any component CSS needed: `import 'kushy-design/semantic/dist/components/button.css'`

### Using Components

1. Import the component: `import { Button } from 'kushy-design'
2. Use it: `<Button />`

### Using SUI React Components

Use any SUI React components as needed. Make sure to import CSS (either compiled/master file or component-based CSS).

```js
import React from 'react'
import { Table } from 'semantic-ui-react'

import 'kushy-design/semantic/dist/components/table.min.css'

export default ({ section }) => {

  const headerItemsCollection = {
    'topicals': [
      'Name',
      'List Price',
      'Sales Price',
    ],
  }

  const headerItems = headerItemsCollection[section].map(headerItem => (
    <Table.HeaderCell>{ headerItem }</Table.HeaderCell>
  ))

  return (
      <React.Fragment>
        <Table.Row>
          <Table.HeaderCell colSpan={ headerItems.length }>
            { section }
          </Table.HeaderCell>
        </Table.Row>
        <Table.Row>
            { headerItems }
        </Table.Row>
      </React.Fragment>
  )
}

```

## Development

### Quick Start

1. `git clone https://github.com/kushyapp/kushy-design.git`
1. `cd kushy-design`
1. `npm install`
1. `npm install gulp-cli -g && npm install gulp -D`

> Gulp is required by Semantic UI to build the CSS and JS files after modifying with new properties.

### Modifying CSS

1. Change any CSS overrides/variables in the SUI theme (`semantic/src/themes/kushy-v1`)
1. Build CSS - `cd semantic && gulp build`
1. Commit changes to master + push to repo

## Documentation

All the documentation for this design system is locally based. You can find all the raw documentation in Markdown format in the `/docs/` folder. These files are imported into another project that handles the build process, since documentation theming can be fickle - and will be dramatically changed over time.

## NPM

To publish to NPM, run these commands inside project:

1. `npm login`
1. `npm version <update_type>`
1. `npm publish`