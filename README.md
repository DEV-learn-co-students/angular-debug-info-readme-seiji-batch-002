# Disable debug info

## Overview

You might've noticed all these `ng-scope` and `ng-binding` classes. These are for our test runners to be able to run properly. However, in production, we don't need these. Let's turn them off!

## Objectives

- Describe debug info
- Disable debug info in production

## Disabling debug info

Much like applyAsync, it's just a simple configuration switch.

We use `$compileProvider` and call `debugInfoEnabled` with false, turning it off.

```js
angular
	.module('app')
	.config(function ($compileProvider) {
        $compileProvider.debugInfoEnabled(true);
	});
```

Now that we've done that, you'll no longer see any classes or comments added anywhere. Awesome! A little overhead, but in the long run, makes things a lot faster.