# Petfinder JS SDK

[![CircleCI](https://circleci.com/gh/petfinder-com/petfinder-js-sdk.svg?style=shield)](https://circleci.com/gh/petfinder-com/petfinder-js-sdk)
[![npm version](https://img.shields.io/npm/v/@petfinder/petfinder-js.svg)](https://www.npmjs.com/package/@petfinder/petfinder-js)
[![Coverage Status](https://coveralls.io/repos/github/petfinder-com/petfinder-js-sdk/badge.svg?branch=feature%2Fcoveralls)](https://coveralls.io/github/petfinder-com/petfinder-js-sdk?branch=feature%2Fcoveralls)

A JS wrapper for the Petfinder API, written in JavaScript/TypeScript.

## Features

* TypeScript definition
* Promises (via [Axios](https://github.com/axios/axios))
* Well tested

## Install

Using npm:

    npm install --save @petfinder/petfinder-js

In browser:

```html
<script src="https://unpkg.com/axios/dist/axios.min.js"></script>
<script src="https://unpkg.com/@petfinder/petfinder-js/dist/petfinder.min.js"></script>
```

## Usage (Browser)

```js
var pf = new petfinder.Client({apiKey: "my-api-key", secret: "my-api-secret"});

pf.animal.search()
    .then(function (response) {
        // Do something with `response.data.animals`
    })
    .catch(function (error) {
        // Handle the error
    });
```

Another way if you have issues with the above code snippet and using React

```js
export const getAllPets = async () => {
  const pf = new Client({
    apiKey: "my-api-key",
    secret: "my-api-secret",
  });

  return (await pf.animal.search()).data;
};
```

## Usage (Node/CommonJS)

```js
var petfinder = require("@petfinder/petfinder-js");
var client = new petfinder.Client({apiKey: "my-api-key", secret: "my-api-secret"});

client.animal.search()
    .then(function (response) {
        // Do something with `response.data.animals`
    })
    .catch(function (error) {
        // Handle the error
    });
```

## Usage (TypeScript/ES6 Module)

```js
import { Client } from "@petfinder/petfinder-js";

const client = new Client({apiKey: "my-api-key", secret: "my-api-secret"});

client.animal.search()
    .then(function (response) {
        // Do something with `response.data.animals`
    })
    .catch(function (error) {
        // Handle the error
    });
```

## If using primary_photo_cropped, some dogs or cats won't have images. I recommend adding a placeholder like below example if using React

```jsx

<img
            src={
            animal.primary_photo_cropped
              ? animal.primary_photo_cropped.small
              : "https://source.unsplash.com/1600x900/?pets"
          }
          alt=""
        />

```

## Documentation

See [docs directory](docs/) for more detailed documentation.
