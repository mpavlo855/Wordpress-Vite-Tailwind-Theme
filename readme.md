# Boilerplate Wordpress Theme with Tailwindcss & Vite

Example of using Vite + TailwindCSS in Wordpress Theme development. Auto generating CSS, auto refresh on every file save/edit and easy production build tool with no hassle.
Inspired by https://github.com/vitejs/vite/issues/341

<img src="assets/img/hello-world.jpg" width="100%">

## Main features

- fast Auto browser refresh/sync file change/save
- built in Tailwindcss Just-in-time compiler
- extremely small CSS as there is no unsued css at all
- keep your local domain while developing
- `npm run build` for production packing Javascript and CSS

## Installation (Node.js/npm required):

Clone or Unpack and copy folder to your Wordpress installation /wp-content/themes/ folder, or install theme via wp-admin by uploading .zip file and activate the theme.
Then from your console or command prompt go to the theme folder and run **npm install**. Note: NodeJS is requred.

```bash
npm install
```

Quick commands:
```bash
# dev server start
npm run dev

# production build
npm run build
```

## Setup

Entry point file **main.js** is where you include all your scripts and styles. It can be changed via **vite.config.json** and **functions.php**.

```bash
# get styles
import "./assets/css/styles.css"

# get scripts
import "./assets/js/scripts.js"
```

## Development with live preview/refresh

Ensure **define("IS_VITE_DEVELOPMENT", true);** exists in your **wp-config.php** or theme/plugin **functions.php**. Just run **npm run dev** and refresh your development website.

```bash
npm run dev
```
After Vite dev server is started open your installed Wordpress website in any browser or refresh it. Then you can start editing index.php, or any other php file in your theme, by adding elements and Tailwind classes. After saving changes your browser page eg your site should refresh immediately. You can freely edit asset files like styles.css, scripts.js too.


## Production build

Just run **npm run build**, set defined **IS_VITE_DEVELOPMENT** to **false** and refresh local website.

```bash
npm run build
```
Wordpress should load now production generated assets.

Note: To ensure classes used inside CMS to be processed just add them to safelist.txt and run build again.


## Sass / Less

CSS Pre-processors are also supported by ViteJS

```bash
# .scss and .sass
npm add -D sass

# .less
npm add -D less
```

Please check link for details.
https://vitejs.dev/guide/features#css-pre-processors


## Note for httpS serving
If your local development domain is served via **https**:// then generating certificate for localhost usage and some changes in config are required
- install mkcert utility and follow the instructions how to generate & install certificate https://github.com/FiloSottile/mkcert
    - example on Windows 10 (PowerShell as Administrator)

```bash
# install mkcert
choco install mkcert

# global one time install
mkcert -install

# run in project/theme folder to create localhost-key.pem & localhost.pem 
mkcert localhost
```

- enable server.https option in **vite.config.js**
- change VITE_SERVER to http**s** in your **inc/inc.vite.php**




## Customizations

More info on the links below
- https://vitejs.dev/config/
- https://tailwindcss.com/

Visual Studio Code Tailwind Intellisense plugin is a must.
https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss
