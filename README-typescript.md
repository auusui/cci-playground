# Typescript

The ts/ subdirectory supports Typescript solutions using [ESLint](https://eslint.org/) as a coding standard, and [Mocha](https://mochajs.org/) and [Chai](https://www.chaijs.com/) for testing. The code can be written using ES7 constructs (such as import and export) and run in Node using [ts-node](https://github.com/TypeStrong/ts-node) and [ts-mocha](https://github.com/piotrwitek/ts-mocha).

## 1. Install Node.

You must have Node installed on your computer. See [Install Node](https://nodejs.org/en/download/) for details.

## 2. Install node libraries.

Change directories to cci-playground/ts, then invoke `npm install`:

```
~/g/i/c/ts (master|…) $ npm install
added 494 packages from 758 contributors and audited 3361 packages in 5.965s
found 0 vulnerabilities

~/g/i/c/ts (master|…) $
```

## 3. Create an IntelliJ IDEA (or WebStorm) project

Set up a project that points to the ts/ directory in IntelliJ, then open the IsUnique.ts file. It should look like this:

<img src="https://github.com/ics-software-engineering/cci-playground/raw/master/images/ts-intellij-isunique.ts.png">


## 4. Run the tests

A nice way to develop your solutions is to write a set of tests to check that your code performs as expected. For example, here is a file containing a couple of simple tests of my IsUnique solution:

<img src="https://github.com/ics-software-engineering/cci-playground/raw/master/images/ts-intellij-isunique-test-code.png">

If you click on the double left arrow on line five, you'll get a menu that allows you to "Run IsUnique.test.ts". Unfortunately, the first time you do so, you'll get an error like this:

<img src="https://github.com/ics-software-engineering/cci-playground/raw/master/images/ts-intellij-mocha-error.png">

This error occurs because Node does not understand ES7 constructs like import.  The fix is to select Run > Edit Configurations..., then add '-r ts-node/register' as a Node option:

<img src="https://github.com/ics-software-engineering/cci-playground/raw/master/images/ts-intellij-mocha-config.png">

After adding this config option, you can run the test without error inside IntelliJ:

<img src="https://github.com/ics-software-engineering/cci-playground/raw/master/images/ts-intellij-mocha-success.png">

## 5. Everything from the command line?

Of course you can do everything from the command line:

```
~/g/i/c/ts (master|✔) $ npm run test

> cci-playground-ts@1.0.0 test /Users/philipjohnson/github/philipmjohnson/cci-playground/ts
> ts-mocha *.test.ts

  isUnique
    ✓ should return true for a unique string
    ✓ should return false for a non-unique string

  2 passing (6ms)
~/g/i/c/ts (master|✔) $
```

## 6. Fun with Typescript

Typescript is nice because you get, well, types!  For example, IntelliJ can now autocomplete a function and tell you the types of parameters and the result type:

<img src="https://github.com/ics-software-engineering/cci-playground/raw/master/images/ts-intellij-ts-cool-1.png">

But the real winner is the ability to tell you immediately when you violate type consistency:

<img src="https://github.com/ics-software-engineering/cci-playground/raw/master/images/ts-intellij-ts-cool-2.png">





















