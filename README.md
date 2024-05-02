# @omegion1npm/temporibus-tempora-nemo

[![build status](https://img.shields.io/github/actions/workflow/status/bergos/@omegion1npm/temporibus-tempora-nemo/test.yaml?branch=master)](https://github.com/omegion1npm/temporibus-tempora-nemo/actions/workflows/test.yaml)
[![npm version](https://img.shields.io/npm/v/@omegion1npm/temporibus-tempora-nemo.svg)](https://www.npmjs.com/package/@omegion1npm/temporibus-tempora-nemo)

A protocol handler wrapper for fetch.

## Usage

`@omegion1npm/temporibus-tempora-nemo` doesn't contain any fetch implementations.
A map of protocol to implementation must be given to the constructor.
This example shows how to create a fetch for file, http and https URLs:

```javascript
import fileFetch from 'file-fetch'
import httpFetch from 'nodeify-fetch'
import protoFetch from '@omegion1npm/temporibus-tempora-nemo'

const fetch = protoFetch({
  [null]: fileFetch,
  file: fileFetch,
  http: httpFetch,
  https: httpFetch
})

const res = await fetch(`file://${process.cwd()}/package.json`)
``` 
