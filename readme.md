# gulp-cordova-create

> Create a cordova project


## Installation

```
npm install --save-dev gulp-cordova-create
```


## Usage

```js
const create = require('gulp-cordova-create');

gulp.task('build', () => {
    return gulp.src('dist')
        .pipe(create());
});
```

This will generate a Cordova project in the `.cordova` directory. It will copy the contents of the `dist` directory
to the `www` directory of the cordova project.

### Options

You can pass in extra options to change the initial configuration of the project.

```js
const create = require('gulp-cordova-create');

gulp.task('build', () => {
    const options = {
        dir: 'myproject',
        id: 'com.myproject.hello',
        name: 'MyProject'
    };

    return gulp.src('dist')
        .pipe(create(options));
});
```

This will execute the following command

```
$ cordova create myproject com.myproject.hello MyProject
```

And then it will copy the content of the `dist` directory to the `www` directory of the cordova project.


## API

### create([options])

#### options

##### dir

Type: `string`<br>
Default: `.cordova`

The name of the output directory.

##### id

Type: `string`<br>
Default: `io.cordova.hellocordova`

The reverse domain-style identifier of the project.

##### name

Type: `string`<br>
Default: `HelloCordova`

The application's display title.

##### buildConfig

Type: `object`<br>
Default: `undefined`

Content to include in the cordova `build.json`. <br>
See `Using build.json` section of cordova documentation for posible configurations.



## Related

See [`gulp-cordova`](https://github.com/SamVerschueren/gulp-cordova) for the full list of available packages.


## License

MIT © Sam Verschueren
