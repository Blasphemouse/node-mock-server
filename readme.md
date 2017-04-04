
# node-mock-server

> File based Node API mock server

[![Build status](https://img.shields.io/travis/smollweide/node-mock-server/master.svg)](https://travis-ci.org/smollweide/node-mock-server)
[![Build status](https://ci.appveyor.com/api/projects/status/tfluudfe4s7810w8/branch/master?svg=true)](https://ci.appveyor.com/project/smollweide/node-mock-server/branch/master)
[![Dependencies](https://img.shields.io/david/smollweide/node-mock-server/master.svg)](https://david-dm.org/smollweide/node-mock-server)
[![npm](https://badge.fury.io/js/node-mock-server.svg)](https://badge.fury.io/js/node-mock-server)
[![npm](https://img.shields.io/npm/dt/node-mock-server.svg)](https://www.npmjs.com/package/node-mock-server)

![node-mock-server-ui.png](https://cloud.githubusercontent.com/assets/2912007/13898299/0ad93a76-edcd-11e5-8eb8-840471a0835b.png)

## Features
- Node.js and file based ([folder structure](/doc/readme-folder-structure.md))
- API documentation UI
- [Functions in mock data](/doc/readme-mock-functions.md)
- [Faker included](/doc/readme-faker.md)
- [Query params in mock data](/doc/readme-query-params.md)
- [Dynamic path params in mock data](/doc/readme-path-params.md)
- [Multiple expected responses](/doc/readme-expected-response.md)
- [Error cases](/doc/readme-expected-response.md)
- [Swagger import](/doc/readme-swagger-import.md)
    - DTO import
    - DTO response function
- [Response validation](/doc/readme-response-validation.md)
- [Response header](/doc/readme-response-header.md)
- [DTO to Class converter]()

## Getting Started
This application requires Node `0.12` or higher

```shell
brew install node
```

```shell
npm install node-mock-server --save-dev
```

```shell
node app.js
```

## The "app.js" file

### Overview
In your project's root, add a file named for example `app.js`.

```js
var mockServer = require('node-mock-server');
mockServer(options);
```

### Options
[node-mock-server options](/doc/readme-options.md)

### Usage Examples

#### Default Options

```js
var mockServer = require('node-mock-server');
mockServer({});
```

#### Custom Options

```js
var mockServer = require('node-mock-server');
mockServer({
	restPath: __dirname + '/mock/rest',
	dirName: __dirname,
    title: 'Api mock server',
    version: 2,
    urlBase: 'http://localhost:3003',
    urlPath: '/rest/v2',
    port: 3003,
    funcPath: __dirname + '/func',
    headers: {
    	'Global-Custom-Header': 'Global-Custom-Header'
    },
    customDTOToClassTemplate: __dirname + '/templates/dto_es6flow.ejs',
    swaggerImport: {
    	protocol: 'http',
    	authUser: undefined,
    	authPass: undefined,
    	host: 'localhost',
    	port: 3001,
    	path: '/src/swagger/swagger-demo-docs.json',
    	dest: dest,
    	replacePathsStr: '/v2/{baseSiteId}',
    	createErrorFile: true,
    	createEmptyFile: true,
    	overwriteExistingDescriptions: true,
    	responseFuncPath: __dirname + '/func-imported'
    }
});
```

## License
[MIT License](https://github.com/smollweide/node-mock-server/blob/master/LICENSE)

## Changelog
Please see the [Releases](https://github.com/smollweide/node-mock-server/releases)
