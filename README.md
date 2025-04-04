### TYPESCRIPT SDK

Demo for publishing TypeScript SDK

Steps followed: 

1. Install necessary npm packages
- ```npm install microbundle```

Microbundle - Microbundle is a tool used for bundling JavaScript code into a single, self-contained file that can be used in web applications or other software projects.
It is particularly useful for developing libraries or modules that need to be distributed in a standalone format.

- ```npm install typescript@latest -g```

- ```npm install isomorphic-unfetch```

2. Update package.json

``` 
{
  "name": "@isupreetk/typescript-sdk",
  "version": "1.0.1",
  "description": "`npm run build`",
  "keywords": [],
  "homepage": "https://github.com/isupreetk/typescript-sdk-demo#readme",
  "bugs": {
    "url": "https://github.com/isupreetk/typescript-sdk-demo/issues"
  },
  "repository": {
    "type": "git",
    "url": "git+ssh://git@github.com/isupreetk/typescript-sdk-demo.git"
  },
  "publishConfig": {
    "access": "public"
  },
  "license": "MIT",
  "author": "isupreetk",
  "type": "commonjs",
  "exports": {
    "require": "./dist/index.js",
    "default": "./dist/index.modern.js"
  },
  "main": "dist/index.js",
  "types": "dist/index.d.ts",
  "files": [
    "dist"
  ],
  "scripts": {
    "build": "rm -rf dist && microbundle --tsconfig tsconfig.json --no-sourcemap",
    "dev": "microbundle --watch --tsconfig tsconfig.json --no-sourcemap"
  },
  "dependencies": {
    "isomorphic-unfetch": "^4.0.2",
    "typescript": "^5.0.4"
  },
  "devDependencies": {
    "microbundle": "^0.15.1"
  },
  "module": "dist/index.m.js",
  "unpkg": "dist/index.umd.js"
}
```

3. Build SDK to get a dist folder.

```npm run build```

4. Log in to your NPM account from the command line

```npm login```

5. You can test your package locally using the ```npm link``` command to create a symbolic link from your package to your local node_modules directory.

6. Run the command ```npm init --scope=isupreetk```

7. Publish package to NPM registry

```npm publish --access-public```