# Mockitup svelte template

A test to set up a degit template for quick creation of Svelte mockups embedded into existing apps

## Create new directory/repo

```
// create new directory
npx degit swiftaff/mockitup-svelte-template <new-project-directory-name>

// install node_modules dependencies
npm i

// commit benchmark files to git
git init
git add -A
git commit -m "first commit"
```

## Generate singleFileExport.html as basis for the mockup

1. Install this Firefox extension: https://github.com/gildas-lormeau/SingleFile
1. Use the extension to download the html file
1. Open it in a browser and check it works
1. Save it over ./index.html
1. TODO - look at using the zip version instead to retain assets as files
    1. Warning - the file will probably be very large and slow to edit as it includes encoded images.
    1. Warning - the file will reformat if using, e.g. Prettier - again taking a long time to save
    1. Warning - the file may contain slightly broken html - use VS Code 'Problems' tab to discover and fix these
1. Insert svelte script into body where mockup element should appear in dom

```
<div id="app"></div>
<script type="module" src="/src/main.js"></script>
```

## Run dev server

1. `npm run dev`
2. visit dev site as shown in terminal, e.g. `localhost:3000`
3. Confirm it displays the default svelte app in the right place - git commit new benchmark

## Start designing your app

1. Edit svelte files in the ./src directory
2. git commit each milestone achievement as you go
3. Manually take screengrabs / copy markup as needed for your project

## TODO preview it somewhere like vercel
