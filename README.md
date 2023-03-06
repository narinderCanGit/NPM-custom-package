How to Create a NPM Package,
Follow the steps below to create your package.

1. Install Node: 
If you do not already have Node installed, you should go ahead and install it. You can visit the official website to download and install Node.js. NPM comes pre-installed with Node.

2. Initialize a Git Repository
Create a new project folder for your package and navigate into the folder. Then, run the following command in your terminal:

  git init - 
This will help you track the changes you make to your package. Also, make sure you have a remote version of your repository on GitHub (or your preferred hosting service).

3. Initialize NPM in Your Project
To do this, navigate to the root directory of your project and run the following command:

  npm init - 
This command will create a package.json file. 
Package name should be unique. Try @<username>/<package_name>

4. Add Your Code
Now, you can go ahead and add the code for your package.

First, you need to create the file that will be loaded when your module is required by another application. For this tutorial, that will be the index.js file.

Inside the index.js file, add the code for your package.

For this tutorial, I will be creating a simple package called @narinder11/npm_custom_package. This package returns the string "Hurray!! You have successfully created a npm package".

//index.js

  function helloNpm() {
    return "Hurray!! You have successfully created a npm package"
  }
  
  module.exports = helloNpm
  
After creating your function, you should export it like in the example above. That way, anyone who downloads your package can load and use it in their code.

If you have been following along, you should now have your package created. But before you publish, you need to test your package. Testing your package reduces the chances of publishing bugs to the NPM registry.


How to Test Your NPM Package
Testing ensures that your NPM package works as expected. There are many ways to test your package. In this tutorial, you will learn one of the simplest ways of testing.

First, navigate to the root of your package project. Then, run the following command:

npm link
This will make your package available globally. And you can require the package in a different project to test it out.

Create a test folder. And inside that test folder, add a script.js file.

The test folder contains only the script.js file. It does not yet contain the package. To add the package you created to your test folder, run the command below:

npm link <name-of-package>
In the case of the test folder for this tutorial, I will run the following command:

npm link @narinder11/npm_custom_package
This will create a node-modules folder. And it'll add all the files and folders from your package.

In the script.js file, you can now require your package and use it for the test.

// test/script.js

const helloNpm = require('@narinder11/npm_custom_package')

console.log(helloNpm())

The first-hello-npm package is expected to return the string "Hurray!! You have successfully created a npm package". As you can see from the screenshot below, the package works as expected when I run the script.

After testing your package and ensuring it works as expected, you can now publish it on the NPM registry.


How to Publish Your NPM Package
To publish your package on the NPM registry, you need to have an account. If you don't have an account, visit the NPM sign up page to create one.

After creating the account, open your terminal and run the following command in the root of your package:

npm login
You will get a prompt to enter your username and password. If login is successful, you should see a message like this:

Logged in as <your-username> on https://registry.npmjs.org/.

You can now run the following command to publish your package on the NPM registry:

npm publish
If all goes well, you should get results.

Notice indicating that the package is published successfully.
If you have been following along, then congratulations! You just published your first NPM package.

You can visit the NPM website and run a search for your package. You should see your package show up in the search results.

package-available
The @narinder11/npm_custom_package package is now available on NPM
