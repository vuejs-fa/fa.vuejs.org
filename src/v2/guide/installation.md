---
title:  نصب
type: guide
order: 1
vue_version: 2.5.16
gz_size: "30.90"
---

### سازگاری با مرورگر‌ها

ویو از ‌<span title='IE8'>اینترنت اکسپلورر ۸</span> و نسخه های قدیمی‌تر از آن پشتیبانی **نمی‌کند**، چرا که ویو از امکاناتی در ECMAScript 5 استفاده می‌کند که در اینترنت اکسپلور ۸ قابل پیاده‌سازی نیستند. اما ویو از تمام [مروگرهای سازگار با ECMAScript 5](https://caniuse.com/#feat=es5) پشتیبانی می‌کند.

### نسخه منتشر شده

آخرین نسخه پایدار: {{vue_version}}

جزئیات انتشار و تغییرات هر یک از نسخه های ویو در [گیت‌هاب](https://github.com/vuejs/vue/releases) قابل دسترسی می‌باشد.

## ابزار توسعه دهندگان (Vue Devtools)

  در هنگام توسعه اپلیکیشن ویو ما پیشنهاد می‌کنیم که [Vue Devtools](https://github.com/vuejs/vue-devtools#vue-devtools) را وری مرورگر خود نصب کنید که با محیط کاربری ساده‌اش به شما برای بررسی داده‌ها و خطایابی در اپلیکیشنتان کمک می‌کند.

## استفاده مستقیم از کد ویو با استفاده از تگ `<script>`

کافیست که کد ویو را دانلود کنید و آن را از طریق تگ script به صفحه خود وارد کنید. با این کار `Vue` به عنوان یک <span title='global variable'>متغییر سراسری</span> ثبت شده و در کد شما قابل استفاده خواهد بود. 

<p class="tip"> در هنگام توسعه از نسخه فشرده (minified) استفاده نکنید. چرا که خیلی از هشدارهای مفید در مورد خطاهای رایج را از دست خواهید داد!</p>

<div id="downloads">
  <a class="button" href="/js/vue.js" download>Development Version</a><span class="light info">با تمام هشدارها و حالت خطایاب، مناسب در هنگام توسعه</span>

  <a class="button" href="/js/vue.min.js" download>Production Version</a><span class="light info">هشدارهای کنسول خذف شذه، حجم فشرده {{gz_size}}KB min+gzip، مناسب برای محصول نهایی.</span>
</div>

### استفاده از شبکه تحویل محتوا (CDN)
برای نمونه اولیه و یا یادگیری ویو می توانید به جای دانلود کردن کد از لینک آخرین نسخه در شبکه تحویل محتوا استفاده کنید:

``` html
<script src="https://cdn.jsdelivr.net/npm/vue"></script>
```

برای محصول نهایی،‌ برای اجتناب از خطاهای و ناسازگاری‌های پیش بینی نشده،‌ ما پیشنهاد می کنیم که همیشه از لینک یک نسخه مشخص استفاده کنید:

``` html
<script src="https://cdn.jsdelivr.net/npm/vue@2.6.0/dist/vue.js"></script>
```
اگر از ماژول‌های محلی ES استفاده می‌کنید، همچنین یک نسخه سازگار با ماژول‌های ES هم وجود دارد:

``` html
<script type="module">
  import Vue from 'https://cdn.jsdelivr.net/npm/vue@2.6.0/dist/vue.esm.browser.js'
</script>
```

شما می‌توانید منبع کد بسته NPM موجود در شبکه تحولی محتوا را در [cdn.jsdelivr.net/npm/vue](https://cdn.jsdelivr.net/npm/vue/) بررسی کنید.

به غیر از  jsdeliver کد ویو همچنین در شبکه های تحویل محتوای [unpkg](https://unpkg.com/vue@{{vue_version}}/dist/vue.js) و [cdnjs](https://cdnjs.cloudflare.com/ajax/libs/vue/{{vue_version}}/vue.js) نیز در دسترس می‌باشد. (نسخه نهایی بعد از انتشار کمی با تاخیر در cdnjs قابل دسترسی خواهد بود).

حتما درباره [نسخه‌های ساخت متفاوت ویو](#Explanation-of-Different-Builds) بخوانید و با تغییر `vue.js` به `vue.min.js` از **نسخه محصول نهایی (production version)** در وبسایت نهایی‌تان استفاده کنید. این کد فشرده شده با حجمی کمتر به جای در نظر گرفتن تجربه توسعه دهنده‌گان، برای سرعت بالاتر بهینه سازی شده است.
## NPM

برای ساخت اپلیکیشن‌هایی در مقیاس بزرگ به وسیله ویو، روش توصیه شده برای نصب ویو NPM است. این روش به خوبی با اپلیکیشن هایی که برای ترکیب و بسته بندی ماژول ها به کار می‌روند،‌ مانند [Webpack](https://webpack.js.org/) و یا [Browserify](http://browserify.org/) سازگار است. ویو همچنین ابزارهایی برای تولید [<span title='Single File Components'>قطعه کد‌های تک فایلی</span>](single-file-components.html) ارائه می‌کند.

``` bash
# latest stable
$ npm install vue
```

## واسط خط فرمان (CLI)

ویو یک [CLI  رسمی](https://github.com/vuejs/vue-cli) ارائه می‌دهد که می‌توان از آن برای تولید سریع چهارچوب <span title='Single Page Applications'>اپلیکیشن‌های تک صفحه</span> قدرتمند استفاده کرد.این CLI همچنین ابزار مورد نیاز برای تمامی مراحل تولید در روند نوین توسعه اپلیکینش فرانت‌اند را فراهم می‌کند. با استفاده از واسط خط فرمان ویو فقط چند دقیقه زمان می‌برد تا محیط توسعه را با امکاناتی برای به روز رسانی اتوماتیک صفحه اپلیکیشن (hot-reload)، کنترل و تصحیح سینتکس ها در هنگام دخیره کردن فایل (lint-on-save) و تولید فایل کد آماده برای محصول نهایی بر پا کنید. برای جزئیات بیشتر [راهنمای CLI ویو](https://cli.vuejs.org) را مطالعه کنید.

<p class="tip">The CLI assumes prior knowledge of Node.js and the associated build tools. If you are new to Vue or front-end build tools, we strongly suggest going through <a href="./">the guide</a> without any build tools before using the CLI.</p>

<div class="vue-mastery"><a href="https://www.vuemastery.com/courses/real-world-vue-js/vue-cli" target="_blank" rel="noopener" title="Vue CLI">Watch a video explanation on Vue Mastery</a></div>

## Explanation of Different Builds

In the [`dist/` directory of the NPM package](https://cdn.jsdelivr.net/npm/vue/dist/) you will find many different builds of Vue.js. Here's an overview of the difference between them:

| | UMD | CommonJS | ES Module (for bundlers) | ES Module (for browsers) |
| --- | --- | --- | --- | --- |
| **Full** | vue.js | vue.common.js | vue.esm.js | vue.esm.browser.js |
| **Runtime-only** | vue.runtime.js | vue.runtime.common.js | vue.runtime.esm.js | - |
| **Full (production)** | vue.min.js | - | - | vue.esm.browser.min.js |
| **Runtime-only (production)** | vue.runtime.min.js | - | - | - |

### Terms

- **Full**: builds that contain both the compiler and the runtime.

- **Compiler**: code that is responsible for compiling template strings into JavaScript render functions.

- **Runtime**: code that is responsible for creating Vue instances, rendering and patching virtual DOM, etc. Basically everything minus the compiler.

- **[UMD](https://github.com/umdjs/umd)**: UMD builds can be used directly in the browser via a `<script>` tag. The default file from jsDelivr CDN at [https://cdn.jsdelivr.net/npm/vue](https://cdn.jsdelivr.net/npm/vue) is the Runtime + Compiler UMD build (`vue.js`).

- **[CommonJS](http://wiki.commonjs.org/wiki/Modules/1.1)**: CommonJS builds are intended for use with older bundlers like [browserify](http://browserify.org/) or [webpack 1](https://webpack.github.io). The default file for these bundlers (`pkg.main`) is the Runtime only CommonJS build (`vue.runtime.common.js`).

- **[ES Module](http://exploringjs.com/es6/ch_modules.html)**: starting in 2.6 Vue provides two ES Modules (ESM) builds:

  - ESM for bundlers: intended for use with modern bundlers like [webpack 2](https://webpack.js.org) or [Rollup](https://rollupjs.org/). ESM format is designed to be statically analyzable so the bundlers can take advantage of that to perform "tree-shaking" and eliminate unused code from your final bundle. The default file for these bundlers (`pkg.module`) is the Runtime only ES Module build (`vue.runtime.esm.js`).

  - ESM for browsers (2.6+ only): intended for direct imports in modern browsers via `<script type="module">`.

### Runtime + Compiler vs. Runtime-only

If you need to compile templates on the client (e.g. passing a string to the `template` option, or mounting to an element using its in-DOM HTML as the template), you will need the compiler and thus the full build:

``` js
// this requires the compiler
new Vue({
  template: '<div>{{ hi }}</div>'
})

// this does not
new Vue({
  render (h) {
    return h('div', this.hi)
  }
})
```

When using `vue-loader` or `vueify`, templates inside `*.vue` files are pre-compiled into JavaScript at build time. You don't really need the compiler in the final bundle, and can therefore use the runtime-only build.

Since the runtime-only builds are roughly 30% lighter-weight than their full-build counterparts, you should use it whenever you can. If you still wish to use the full build instead, you need to configure an alias in your bundler:

#### Webpack

``` js
module.exports = {
  // ...
  resolve: {
    alias: {
      'vue$': 'vue/dist/vue.esm.js' // 'vue/dist/vue.common.js' for webpack 1
    }
  }
}
```

#### Rollup

``` js
const alias = require('rollup-plugin-alias')

rollup({
  // ...
  plugins: [
    alias({
      'vue': require.resolve('vue/dist/vue.esm.js')
    })
  ]
})
```

#### Browserify

Add to your project's `package.json`:

``` js
{
  // ...
  "browser": {
    "vue": "vue/dist/vue.common.js"
  }
}
```

#### Parcel

Add to your project's `package.json`:

``` js
{
  // ...
  "alias": {
    "vue" : "./node_modules/vue/dist/vue.common.js"
  }
}
```

### Development vs. Production Mode

Development/production modes are hard-coded for the UMD builds: the un-minified files are for development, and the minified files are for production.

CommonJS and ES Module builds are intended for bundlers, therefore we don't provide minified versions for them. You will be responsible for minifying the final bundle yourself.

CommonJS and ES Module builds also preserve raw checks for `process.env.NODE_ENV` to determine the mode they should run in. You should use appropriate bundler configurations to replace these environment variables in order to control which mode Vue will run in. Replacing `process.env.NODE_ENV` with string literals also allows minifiers like UglifyJS to completely drop the development-only code blocks, reducing final file size.

#### Webpack

In Webpack 4+, you can use the `mode` option:

``` js
module.exports = {
  mode: 'production'
}
```

But in Webpack 3 and earlier, you'll need to use [DefinePlugin](https://webpack.js.org/plugins/define-plugin/):

``` js
var webpack = require('webpack')

module.exports = {
  // ...
  plugins: [
    // ...
    new webpack.DefinePlugin({
      'process.env': {
        NODE_ENV: JSON.stringify('production')
      }
    })
  ]
}
```

#### Rollup

Use [rollup-plugin-replace](https://github.com/rollup/rollup-plugin-replace):

``` js
const replace = require('rollup-plugin-replace')

rollup({
  // ...
  plugins: [
    replace({
      'process.env.NODE_ENV': JSON.stringify('production')
    })
  ]
}).then(...)
```

#### Browserify

Apply a global [envify](https://github.com/hughsk/envify) transform to your bundle.

``` bash
NODE_ENV=production browserify -g envify -e main.js | uglifyjs -c -m > build.js
```

Also see [Production Deployment Tips](deployment.html).

### CSP environments

Some environments, such as Google Chrome Apps, enforce Content Security Policy (CSP), which prohibits the use of `new Function()` for evaluating expressions. The full build depends on this feature to compile templates, so is unusable in these environments.

On the other hand, the runtime-only build is fully CSP-compliant. When using the runtime-only build with [Webpack + vue-loader](https://github.com/vuejs-templates/webpack-simple) or [Browserify + vueify](https://github.com/vuejs-templates/browserify-simple), your templates will be precompiled into `render` functions which work perfectly in CSP environments.

## Dev Build

**Important**: the built files in GitHub's `/dist` folder are only checked-in during releases. To use Vue from the latest source code on GitHub, you will have to build it yourself!

``` bash
git clone https://github.com/vuejs/vue.git node_modules/vue
cd node_modules/vue
npm install
npm run build
```

## Bower

Only UMD builds are available from Bower.

``` bash
# latest stable
$ bower install vue
```

## AMD Module Loaders

All UMD builds can be used directly as an AMD module.
