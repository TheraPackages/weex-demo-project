
## weex-demo

This a demo project for weex in thera. The sources demonstrate the following features:

1. How to organize your weex project in thera;
2. How to import local tool modules. Ref local.js;
3. How to import sub component modules. Ref footer-bar.vue;
4. How to import third party modules. Ref demo-tool declared in package.json;
5. How to make configuration in `/.thera/launch.json` to customize features like build, mock and more;

Run the following script in the project's root folder to sync [NPM](https://www.npmjs.com/) dependencies declared in package.json to your local system before further operation. Initially there is only one dependency called [demo-tool](https://www.npmjs.com/package/demo-tool) which we created to demonstrate feauture[4] above.

```
npm install
```

Whenever you add new dependencies or update existing ones in package.json, `npm install` script should be executed again to sync them. This is totally the same as the prevalent [NPM](https://www.npmjs.com/) packages. Just feel free to continue your happy journey from this demo.

Lastly you can get the latest release of Thera [here](https://github.com/alibaba/Thera/releases).
