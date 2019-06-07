---
title:  نصب
type: guide
order: 1
vue_version: 2.5.16
gz_size: "30.90"
---

### سازگاری با مرورگر‌ها

ویو از ‌<span title='IE8'>اینترنت اکسپلورر ۸</span> و نسخه‌های قدیمی‌تر از آن پشتیبانی **نمی‌کند**، چرا که ویو از امکاناتی در ECMAScript 5 استفاده می‌کند که در اینترنت اکسپلور ۸ قابل پیاده‌سازی نیستند. اما ویو از تمام [مروگرهای سازگار با ECMAScript 5](https://caniuse.com/#feat=es5) پشتیبانی می‌کند.

### نسخه منتشر شده

آخرین نسخه پایدار: {{vue_version}}

جزئیات انتشار و تغییرات هر یک از نسخه‌های ویو در [گیت‌هاب](https://github.com/vuejs/vue/releases) قابل دسترسی می‌باشد.

## ابزار توسعه دهندگان (Vue Devtools)

  در هنگام توسعه اپلیکیشن ویو ما پیشنهاد می‌کنیم که [Vue Devtools](https://github.com/vuejs/vue-devtools#vue-devtools) را وری مرورگر خود نصب کنید که با محیط کاربری ساده‌اش به شما برای بررسی داده‌ها و خطایابی در اپلیکیشنتان کمک می‌کند.

## استفاده مستقیم از کد ویو با استفاده از تگ `<script>`

کافیست که کد ویو را دانلود کنید و آن را از طریق تگ script به صفحه اضافه کنید. با این کار `Vue` به عنوان یک <span title='global variable'>متغییر سراسری</span> ثبت شده و در کد شما قابل استفاده خواهد بود. 

<p class="tip"> در هنگام توسعه از نسخه فشرده (minified) استفاده نکنید. چرا که خیلی از هشدارهای مفید در مورد خطاهای رایج را از دست خواهید داد!</p>

<div id="downloads">
  <a class="button" href="/js/vue.js" download>Development Version</a><span class="light info">با تمام هشدارها و حالت خطایاب، مناسب در هنگام توسعه</span>

  <a class="button" href="/js/vue.min.js" download>Production Version</a><span class="light info">هشدارهای کنسول خذف شذه، حجم فشرده {{gz_size}}KB min+gzip، مناسب برای محصول نهایی.</span>
</div>

### استفاده از شبکه تحویل محتوا (CDN)
برای نمونه اولیه و یا یادگیری ویو می‌توانید به جای دانلود کردن کد از لینک آخرین نسخه در شبکه تحویل محتوا استفاده کنید:

``` html
<script src="https://cdn.jsdelivr.net/npm/vue"></script>
```

در محصول نهایی،‌ برای اجتناب از خطاها و ناسازگاری‌های پیش بینی نشده،‌ ما پیشنهاد می کنیم که همیشه از لینک یک نسخه مشخص استفاده کنید:

``` html
<script src="https://cdn.jsdelivr.net/npm/vue@2.6.0/dist/vue.js"></script>
```
اگر از ماژول‌های محلی ES استفاده می‌کنید، همچنین یک نسخه سازگار با ماژول‌های ES هم وجود دارد:

``` html
<script type="module">
  import Vue from 'https://cdn.jsdelivr.net/npm/vue@2.6.0/dist/vue.esm.browser.js'
</script>
```

شما می‌توانید منبع کد بسته npm موجود در شبکه تحولی محتوا را در [cdn.jsdelivr.net/npm/vue](https://cdn.jsdelivr.net/npm/vue/) بررسی کنید.

به غیر از  jsdeliver کد ویو همچنین در شبکه های تحویل محتوای [unpkg](https://unpkg.com/vue@{{vue_version}}/dist/vue.js) و [cdnjs](https://cdnjs.cloudflare.com/ajax/libs/vue/{{vue_version}}/vue.js) نیز در دسترس می‌باشند. (نسخه‌های جدید بعد از انتشار کمی با تاخیر در cdnjs قابل دسترسی خواهد بود).

حتما درباره [نسخه‌های متفاوت ویو](#Explanation-of-Different-Builds) بخوانید و با تغییر `vue.js` به `vue.min.js` از **نسخه محصول نهایی (production version)** در وبسایت نهایی‌تان استفاده کنید. این کد فشرده شده با حجمی کمتر به جای در نظر گرفتن تجربه توسعه دهنده‌گان، برای سرعت بالاتر بهینه سازی شده است.
## npm

برای ساخت اپلیکیشن‌هایی در مقیاس بزرگ به وسیله ویو، روش توصیه شده برای نصب ویو npm است. این روش به خوبی با اپلیکیشن هایی که برای ترکیب و بسته بندی ماژول ها به کار می‌روند،‌ مانند [Webpack](https://webpack.js.org/) و یا [Browserify](http://browserify.org/) سازگار است. ویو همچنین ابزارهایی برای تولید [<span title='Single File Components'>قطعه کد‌های تک فایلی</span>](single-file-components.html) ارائه می‌کند.

``` bash
# latest stable
$ npm install vue
```

## واسط خط فرمان (CLI)

ویو یک [CLI  رسمی](https://github.com/vuejs/vue-cli) ارائه می‌دهد که می‌توان از آن برای تولید سریع چهارچوب <span title='Single Page Applications'>اپلیکیشن‌های تک صفحه</span> قدرتمند استفاده کرد.این CLI همچنین ابزار مورد نیاز برای تمامی مراحل تولید در روند نوین توسعه اپلیکینش فرانت‌اند را فراهم می‌کند. با استفاده از واسط خط فرمان ویو فقط چند دقیقه زمان می‌برد تا محیط توسعه را با امکاناتی برای به روز رسانی اتوماتیک صفحه اپلیکیشن (hot-reload)، کنترل و تصحیح سینتکس ها در هنگام دخیره کردن فایل (lint-on-save) و تولید فایل کد آماده برای محصول نهایی برپا کنید. برای جزئیات بیشتر [راهنمای CLI ویو](https://cli.vuejs.org) را مطالعه کنید.

<p class="tip">واسط خط فرمان (CLI) مناسب کاربرانی است که با Node.js و <span title='Build tools'>تولیدابزار</span> مربوط به آن آشنایی قبلی دارند. اگر در ویو یا توسعه فرانت تازه‌کار هستید ما توصیه می‌کنیم که قبل از شروع کار با CLI بدون استفاده از هیچ تولیدابزاری این <a href="./">راهنما</a> را مطالعه کنید.</p>

<div class="vue-mastery"><a href="https://www.vuemastery.com/courses/real-world-vue-js/vue-cli" target="_blank" rel="noopener" title="Vue CLI"> این ویدیو را به زبان انگلیسی در  Vue Mastery ببینید.</a></div>


## توضیح نسخه‌های ساخت متفاوت

در فولدر [`dist/` از بسته npm ویو](https://cdn.jsdelivr.net/npm/vue/dist/) نسخه‌های مختلفی از اسکریپت Vue.js وجود دارد. در اینجا تفاوت‌های این نسخه‌ها را مرور می‌کنیم:

| | UMD | CommonJS | ES Module (for bundlers) | ES Module (for browsers) |
| --- | --- | --- | --- | --- |
| **Full** | vue.js | vue.common.js | vue.esm.js | vue.esm.browser.js |
| **Runtime-only** | vue.runtime.js | vue.runtime.common.js | vue.runtime.esm.js | - |
| **Full (production)** | vue.min.js | - | - | vue.esm.browser.min.js |
| **Runtime-only (production)** | vue.runtime.min.js | - | - | - |

### تعاریف


- **Full**: این اسکریپت شامل همه کدهای compiler و runtime است.

- **Compiler**: کدی که مسولیت تبدیل قالب‌های نمایش به تابع‌های جاوااسکریپت را دارد.

- **Runtime**:  کدی که مسولیت ایجاد نمونه شیء‌های Vue، نمایش و هماهنگی مدل نمای مجازی با داده ها و ... را دارد. می‌توان گفت همه چیز به غیر از compiler.

- **[UMD](https://github.com/umdjs/umd)**: اسکریپت‌های UMD را می‌توان مستقیما در مرورگر با استفاده از تگ `<script>` استفاده کرد. فایل پیش‌فرض شبکه تحویل محتوای  jsDelivr در [https://cdn.jsdelivr.net/npm/vue](https://cdn.jsdelivr.net/npm/vue) نسخه Runtime + Compiler UMD (`vue.js`) است.

- **[CommonJS](http://wiki.commonjs.org/wiki/Modules/1.1)**: نسخه‌های CommonJS برای ابزار‌های بسته‌بندی (bundlers) کد قدیمی مانند [browserify](http://browserify.org/) یا [webpack 1](https://webpack.github.io) هستند. فایل پیش‌فرض برای این بسته‌بندها (`pkg.main`)، نسخه Runtime-Only CommonJS (`vue.runtime.common.js`) است.

- **[ES Module](http://exploringjs.com/es6/ch_modules.html)**: از نسخه ۲.۶ ویو دو ماژول ES را نیز ارائه می‌دهد (ESM):
  - **ESM برای ابزارهای بسته‌بندی کد (Bundlers)**:  این ماژول برای استفاده در ابزارهای مدرنی همچون [webpack 2](https://webpack.js.org) و یا [Rollup](https://rollupjs.org/) ارائه شده است. فرمت ESM طوری طراحی شده که قبل از اجرا قابل تحلیل باشد (Statically analyzable) که این امکان را برای ابزارهای بسته‌بندی فراهم می‌کند که کدهای استفاده نشده را از بسته نهایی حذف کنند. فایل پیش‌فرض برای این ابزارهای مدرن  (`pkg.module`) نسخه Runtime only ES Module  (`vue.runtime.esm.js`) است.

  - **ESM برای مرورگرها (از نسخه ۲.۶ به بعد)**: برای استفاده در مرورگرهای مدرن با استفاده از تگ `<script type="module">`.

### مقایسه Runtime + Compiler با Runtime-only

اگر لازم است که قالب را در سمت <span title='client'>سرویس گیرنده</span>  به کدهای نمایش جاوا اسکریپت تبدیل کنید (برای مثال ارسال یک رشته کاراکتر به عنوان بخشی از قالب و یا استفاده از کد HTML یکی از المان های موجود در صفحه به عنوان قالب)، شمابه compiler نیاز خواهید داشت پس لازم است که از نسخه کامل (full build) استفاده کنید:


``` js
// نیاز دارد compiler این کد به
new Vue({
  template: '<div>{{ hi }}</div>'
})

// ندارد compiler اما این کد نیازی به 
new Vue({
  render (h) {
    return h('div', this.hi)
  }
})
```

وقتی از `vue-loader` یا `vueify` استفاده می‌کنیم، کدهای قالب در فایل‌های `*.vue` در زمان ساخت به تابع‌های نمایش جاوااسکریپت تبدیل خواهند شد بنابراین شما در بسته نهایی نیازی به compiler نخواهید داشت و می‌توانید از نسخه runtime-only استفاده کنید.

از آنجا که نسخه‌های runtime-only حدود ۳۰٪ ازنسخه کامل سبکتر هستند، بهتر است تا جای ممکن از آنها استفاده کنید. اما اگر همچنان می‌خواهید که از نسخه کامل استفاده کنید لازم است که یک alias در تنظیمات ابزار بسته بندی کدتان تعریف کنید:

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

این کد را به فایل `package.json` پروژه اضافه کنید:

``` js
{
  // ...
  "browser": {
    "vue": "vue/dist/vue.common.js"
  }
}
```

#### Parcel

این کد را به فایل `package.json` پروژه اضافه کنید:

``` js
{
  // ...
  "alias": {
    "vue" : "./node_modules/vue/dist/vue.common.js"
  }
}
```

### حالت <span title='Development mode'>توسعه</span> و <span title='Production Mode'> محصول نهایی</span>

نسخه‌های UMD برای هر دو حالت اپلیکیشن در حال توسعه (Development mode) و همچنین محصول نهایی (Production) موجود است. فایل فشرده با پسوند `*.min.js` برای محصول نهایی و فایل با فرمت `*.js` که فشرده نشده برای حالت توسعه که همچنین شامل هشدارهای کمکی برای توسعه دهندگان است.
نسخه‌های CommonJS و ES Module به منظور استفاده در ابزارهای بسته‌بندی کد ارائه شده‌اند بنابراین ما نسخه فشرده آن را ارائه نمی‌دهیم و مسولیت فشرده سازی فایل نهایی بر عهده شما است.

فایل‌های CommonJS و ES Module متغییر محیطی `process.env.NODE_ENV` را برای حالتی که باید اجرا شوند را چک می‌کنند.برای تغییر حالتی که می‌خواهید اپلیکیشنتان را اجرا کنید، شما باید تنظیم مربوط به این متغییر محیطی را در ابزاربسته‌بندی کدتان تغییر دهید. تغییر `process.env.NODE_ENV` همچنین به ابزارهای فشرده‌سازی همچون  UglifyJS این امکان را می‌دهد که بلاک های کدی که فقط برای حالت توسعه هستند را به کلی حذف کرده که باعث سبک‌تر شدن حجم فایل نهایی می‌گردد.

#### Webpack

در Webpack از نسخه ۴ به بعد، شما می‌توانید از گزینه `mode` در تنظیمات استفاده کنید:

``` js
module.exports = {
  mode: 'production'
}
```

اما در Webpack نسخه ۳ و قدیمی‌تر، لازم است که از [DefinePlugin](https://webpack.js.org/plugins/define-plugin/) استفاده کنید:

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

از [rollup-plugin-replace](https://github.com/rollup/rollup-plugin-replace) استفاده کنید:

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

از انتقال سراسری [envify](https://github.com/hughsk/envify) روی بسته کدتان استفاده کنید.

``` bash
NODE_ENV=production browserify -g envify -e main.js | uglifyjs -c -m > build.js
```

همچنین [نکات دیپلوی محصول نهایی](deployment.html) را ببینید.

### محیط‌های CSP

برخی محیط‌ها همچون Google Chrome Apps، سیاست امنیت محتوا (CSP) را روی کدها اعمال می‌کنند که استفاده از `new Function()` را برای ارزیابی عبارات منع می‌کند. نسخه کامل (full build) برای تولید قالب به این امکان نیازمند بوده و در نتیجه در این نوع محیط‌ها قابل استفاده نمی‌باشد.

اما از سوی دیگر، در نسخه runtime-only تمام سیاست‌های CSP رعایت شده است. وقتی که از نسخه runtime-only با [Webpack + vue-loader](https://github.com/vuejs-templates/webpack-simple) یا [Browserify + vueify](https://github.com/vuejs-templates/browserify-simple) استفاده می‌کنید، کدهای قالب شما در هنگام ساخت به توابع نمایش `render` جاوا اسکریپت تبدیل شده که به خوبی در محیط‌های CSP کار می‌کند.

## Dev Build

**توجه**: فایل های موجود در فولدر `/dist` گیت‌هاب، تنها در هنگام انتشار نسخه جدید به‌روزرسانی می‌شوند. برای استفاده از ویو بوسیله کدهای موجود در گیت‌هاب لازم است که خودتان فایل‌های اسکریپت را ایجاد کنید!

``` bash
git clone https://github.com/vuejs/vue.git node_modules/vue
cd node_modules/vue
npm install
npm run build
```

## Bower

فقظ نسخه‌های UMD از طریق Bower فابل نصب هستند.

``` bash
# latest stable
$ bower install vue
```

## AMD Module Loaders

تمامی نسخه‌های ساخت UMD را می‌توان مستقیما به عنوان ماژول AMD استفاده کرد.

