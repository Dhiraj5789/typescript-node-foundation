tsc - This script turns our TypeScript code into JavaScript using tsc, and also checks for any errors.

The dev script will be the most complex. 
This script runs all the scripts that start with dev: in parallel.
When we run it, we want to do several things at once:

tsc --watch to bundle our TypeScript code and check for errors.
node --watch to re-run our application when it changes.
For each of these, we will add a separate npm script, then run them all simultaneously using pnpm.

The --watch flag tells TypeScript to re-run when the code changes.

The --preserveWatchOutput flag tells TypeScript not to clear the console output when it re-runs.


esModuleInterop: Helps mend a few of the fences between CommonJS and ES Modules.

skipLibCheck: Skips checking the types of .d.ts files. This is important for performance, because otherwise all node_modules will be checked.

target: The version of JavaScript you're targeting.

allowJs and resolveJsonModule: Allows you to import .js and .json files. Always useful.

moduleDetection: This option forces TypeScript to consider all files as modules. This helps to avoid 'cannot redeclare block-scoped variable' errors.

isolatedModules: This option prevents a few TS features which are unsafe when treating modules as isolated files.

strict: Enables all strict type checking options. Indispensable.

noUncheckedIndexedAccess: Prevents you from accessing an array or object without first checking if it's defined. This is a great way to prevent runtime errors, and should really be included in strict.

outDir: Tells TypeScript where to put the compiled JavaScript files. 

declaration: Tells TypeScript to emit .d.ts files. This is needed so that libraries can get autocomplete on the .js files you're creating.