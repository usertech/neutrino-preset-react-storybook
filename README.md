# `@usertech/neutrino-preset-react-storybook`

This preset sets up react storybook webpack entries and plugins to allow non-duplicated webpack config.


## Installation

    $ yarn add --dev usertech/neutrino-preset-react-storybook#0.0.1


## Usage

### 1. Configure preset

    // .neutrinorc.js
    module.exports = {
        use: [
            ['@usertech/neutrino-preset-react-storybook'],
            ...
        ],
    }

### 2. Add package script


    {
      ...
      "scripts": {
        ...
        "storybook": "neutrino start --options.storybook --options.port 5001",
        ...
      },
      ...
    }


### 3. Create standard [storybook config file](https://github.com/storybooks/storybook/blob/v3.4.11/docs/src/pages/basics/guide-react/index.md#create-the-config-file)

```
$ mkdir .storybook
$ touch .storybook/config.js
```

```
// .storybook/config.js
import { configure } from '@storybook/react';

// Load all files from stories directory
const req = require.context('../stories', true, /\.js$/);
function loadStories() {
	req.keys().forEach(req);
}

configure(loadStories, module);
```
