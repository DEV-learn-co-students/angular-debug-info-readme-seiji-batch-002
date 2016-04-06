# Disable debug info

## Overview

You might've noticed all these `ng-scope` and `ng-binding` classes. These are for our test runners to be able to run properly. However, in production, we don't need these. Let's turn them off!

## Objectives

- Describe debug info
- Disable debug info in production

## Disabling debug info

Load a previous Angular lab and look at it in developer tools. You'll see loads of weird classes. These are there to tell our testing applications what is actually going on inside Angular, so they don't need to dive into the JavaScript code to find out. `ng-binding` tells the testing program that the value is bound to a variable. `ng-scope` is where a new scope has been created. They're not necessary for Angular to function, however.

Much like applyAsync, it's just a simple configuration switch to turn these off.

We use `$compileProvider` and call `debugInfoEnabled` with false, turning it off.

```js
angular
	.module('app')
	.config(function ($compileProvider) {
        $compileProvider.debugInfoEnabled(false);
	});
```

Now that we've done that, you'll no longer see any classes or comments added anywhere. Awesome! A little overhead, but in the long run, makes things a lot faster.

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/angular-debug-info-readme'>Angular Disable Debug Info </a> on Learn.co and start learning to code for free.</p>
