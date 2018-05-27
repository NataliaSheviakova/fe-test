A front-end test of sorts
=================================

A front-end test of sorts is a [React](https://facebook.github.io/react/) application for desktop/mobile devices.

# Contents

* [Installation](#installation)
* [Usage](#usage)
* [Storybook](#storybook)
* [Code](#code)
* [Style](#style)
* [Linting](#linting)

-----
# Installation

```
git clone https://github.com/NataliaSheviakova/catch-design.git
cd catch-design
nvm use
npm install
```

-----
# Usage

    The development build is used - as the name suggests - for development reasons. You have: source maps, debugging and hot reloading ability.

    The production build, on the other hand, runs in production mode. The production build should run uglify and build your source files into one or multiple minimized files. It also extracts CSS and images and other sources loading with webpack. There's also no source maps or hot reloading included.

    // Build your app in dev mode
    npm run build

    // start your app with prod mode
    // TODO: have to be updated if necessary with uglify
    npm run start:prod

    // start you app with dev mode
    npm run start:dev

    // pattern library
    npm run storybook

    // linting
    npm run test:lint

    // TODO; write tests if necessary
    "test": "echo \"No tests available\" && exit 0",

    // husky precommit which will not let us make a commit if we have linting errors in our case
    "precommit": "npm test:lint"

-----
# Storybook

I use [storybook](https://github.com/storybooks/storybook) to serve up pattern library which demonstrates the usage of components, both individually and composed as children of other components.

Storybook can be started and accessed via:

    // The following will serve storybook at http://localhost:9001
    npm run storybook

-----
# Code

## Components
Application code is found in the `./src` directory.

The application is composed of the following components:

* header - the application title

* form - the contact form for a user which connects with CityService to get data for a list of cities

* button component

* separator - dashline which can be used across the app to separate components/blocks visually

* assets - the component that manages state for an asset and all child components (assetList and assetCard).
it's also connecting to AssetService and getting adventure data

* assetList - list of adventures

* assetCard - represents a single instance of an adventure

* gallery - the simple comonent to represent a gallery (works with scrolling on desktop/mobile). It have a connection to GalleryService to get images.

* footer - the component that contains child components such as sharebar, copyright and contactInfo.

## Media Queries
One of the requrements includes a different view for mobile and desktop which has been achieved with using media queries:

    $max-mobile-page-width: 768px;
    $min-desktop-page-width: 769px;

Notice that a viewport size has not been discussed, so the size is using here - something that made more sense during development. Different devices viewport can be found under https://www.mydevice.io/ so you can make a decision what breakpoint to use for your app.

-----
# Style

Styles are found in the `./src/components/theme` directory. They are written in [SASS](http://sass-lang.com/). Classes is structured with [BEM](http://getbem.com/) methodology.

-----
# Linting

```
npm run test:lint
```

This project is set up with [`eslint`](http://eslint.org/) configuration, for its better handling of React's JSX. Your IDE should have an `eslint` plugin or module, or you can run it from the commandline.
