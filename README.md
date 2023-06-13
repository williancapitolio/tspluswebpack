
# tspluswebpack
Repository created to help remember how to use TypeScript and webpack in a project.

Start a project with npm

```bash
  npm init -y
```

Install TypeScript and webpack as development dependencies

```bash
  npm i -D typescript ts-loader webpack webpack-cli
```

Run the command to create the tsconfig.json file

```bash
  npx tsc --init
```

To use only the TypeScript create and run the script

```bash
  "scripts": {
    "tsc": "tsc -w"
```

To use TypeScript and webpack create the webpack.config.js file

```bash
  
const path = require('path');

module.exports = {
  mode: process.env.NODE_ENV,
  entry: './src/index.ts',
  module: {
    rules: [
      {
        test: /\.tsx?$/,
        use: 'ts-loader',
        exclude: /node_modules/,
      },
    ],
  },
  resolve: {
    extensions: ['.tsx', '.ts', '.js'],
  },
  output: {
    filename: 'index.js',
    path: path.resolve(__dirname, 'public', 'dist'),
  },
};
```

To use TypeScript and webpack in a development environment create and run the script

```bash
  "scripts": {
    "dev": "NODE_ENV=development webpack --progress --watch"
```

To use TypeScript and webpack in a production environment, create and run the script

```bash
  "scripts": {
    "prod": "NODE_ENV=production webpack --progress --watch"
```

Excellent! That's all, folks! But hold on...

A desirable folder structure is like:
