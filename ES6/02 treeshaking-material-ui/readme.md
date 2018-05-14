# Tree shaking material ui

This sample start from [01 No tree shaking](../01%20no-treeshaking-material-ui/), in this case we are going to change the way we are making the import
so we can take benefit of webpack tree shaking.

# Steps

Steps to recreate this sample:

- Copy the content from _[01 No tree shaking](../01%20no-treeshaking-material-ui/)_

- First install the packages needed, run from the bash / cmd:

```bash
npm install
```

_[app.jsx](./src/app.jsx)_
```diff
import * as React from 'react';
import { HelloComponent } from './hello';
import { NameEditComponent } from './nameEdit';
-- import {AppBar} from "material-ui";
++ import AppBar from 'material-ui/AppBar';
-- import { MuiThemeProvider } from "material-ui/styles";
++ import MuiThemeProvider from 'material-ui/styles/MuiThemeProvider';
// ...
```

- Second run the _run_ custom command.

```bash
npm run build
```

We have low down the bundle size from 985Kb to 160.5 Kb.

If you like to use barrels, in the next sample we will take a look to a babel plugin that can help us on this.
