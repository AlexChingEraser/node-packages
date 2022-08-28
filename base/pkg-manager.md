# Package Manager
till today, I come up with two package mangager:

- `npm`: https://docs.npmjs.com/

- `cnpm`: taobao npm mirror source, https://cnpmjs.org/
```powershell
 npm install -g cnpm --registry=https://registry.npmmirror.com
```

- `yarn` https://yarnpkg.com/getting-started

you will see that package always provide these package manager download/add cli, like
- `npm install package-name`: a useful tool: `npm-check-updates`, and Node packages follow semantic versioning: `major.minor.patch`
  
- `yarn install package-name`

## npm
- `npm install [-g] <package-name@specific-version> [--save, --save-dev]`: install a package from npm registry
- `npm list [--depth=0]`: list your node app dependencies or gloabal
- `npm view <package-you-interested> [dependencies] [versions]`: view some info about some packages
- `npm [-g] outdated`: find your packages dated or outdated
```powershell
PS C:\Users\AlexC> npm -g outdated
Package             Current   Wanted  Latest  Location
@vue/cli             4.5.13   4.5.15  4.5.15  global
jsdoc                 3.6.7   3.6.10  3.6.10  global
npm                 6.14.15  6.14.16   8.4.0  global
typescript            4.5.4    4.5.5   4.5.5  global
webpack              5.58.2   5.67.0  5.67.0  global
webpack-cli           4.9.1    4.9.2   4.9.2  global
webpack-dev-server    4.3.1    4.7.3   4.7.3  global
```
- `npm update`: update your node app toward `package.json`
- `npm uninstall <package-you-want-to-uninstall>`: uninstall package
- `npm login`: login to npmjs
- `npm pushlish`: publish your node app to npm registry
- `npm version [major|minor|patch]`: update a tag verion about your node app version