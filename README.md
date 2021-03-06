# Heroku Buildpack Grunt

A simple buildpack, designed to run with the [multi buildpack](https://github.com/ddollar/heroku-buildpack-multi),
which will run install grunt and run `grunt heroku`.

## Usage

1. Set your buildpack to the [multi buildpack](https://github.com/ddollar/heroku-buildpack-multi):

   ```bash
   $ heroku config:set BUILDPACK_URL=https://github.com/ddollar/heroku-buildpack-multi
   ```

2. Configure your `.buildpacks` file:

   ```
   https://github.com/heroku/heroku-buildpack-nodejs
   https://github.com/ejholmes/heroku-buildpack-grunt
   ```

3. Ensure that npm installs grunt:

   ```json
   {
     "dependencies": {
       "grunt": "latest",
       "grunt-cli": "latest"
     }
   }
   ```

4. Ensure that you have a `heroku` grunt task:

   ```js
   grunt.registerTask('heroku', ['build']);
   ```
