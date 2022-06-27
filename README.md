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

1. For convenience, or if the site/page is authenticated, use the Firefox extension to download the page as a ZIP: `https://addons.mozilla.org/firefox/addon/singlefilez`
1. OR, assuming the page is public you can install peer dependency single-filez-cli: `https://github.com/gildas-lormeau/single-filez-cli#run` [^bignote]
    1. npm install -g "gildas-lormeau/single-filez-cli" - if this doesn't work:
        1. cd C:\Users\<username>\AppData\Roaming\npm\node_modules
        1. npm install "gildas-lormeau/single-filez-cli"
        1. npm i
    1. add "C:\Users\<username>\AppData\Roaming\npm\node_modules\single-filez-cli" to your environment variables PATH
    1. `cd public`
    1. TODO: it only works on public pages - if you need to access password protected then look at using cookies option in puppeteer?
    1. run it - probably need to use the browser executable option to find chrome `single-filez https://www.ibc.com.au export.html --browser-executable-path "C:\Program Files (x86)\Google\Chrome\Application\Chrome.exe"`
1. Open the exported zip file in a browser and check it works
1. Rename `export.html` to `export.zip`
1. unzip the contents of the zip - so that the assets are saved in the `public` directory
1. move the `index.html` file to the root
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

1. git commit a benchmark of the current page
1. Edit svelte files in the ./src directory
1. git commit each milestone achievement as you go
1. Manually take screengrabs / copy markup as needed for your project

## TODO preview it somewhere like vercel

[^bignote]: Installing the cli version means you no longer have to use the 2nd firefox extension as below...

    1. Install this Firefox extension: https://github.com/gildas-lormeau/SingleFile
    1. Use the extension to download the html file
        1. Warning - the file will probably be very large and slow to edit as it includes encoded images.
        1. Warning - the file will reformat if using, e.g. Prettier - again taking a long time to save
        1. Warning - the file may contain slightly broken html - use VS Code 'Problems' tab to discover and fix these
