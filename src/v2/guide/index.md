---
title: مقدمه
type: guide
order: 2
---

## ویو.جی اس چیست؟


 ویو (Vue) یک **فریم ورک تکاملی** جاوا اسکریپت برای تولید واسط کاربری تحت وب است. برخلاف فریم ورک‌های یکپارچه، ویو از پایه به گونه‌ای طراحی شده است که با توجه به نیاز برنامه، مرحله به مرحله قابل تطبیق باشد. هسته مرکزی لایبری فقط روی لایه نمایش (view) متمرکز است و می‌توان به راحتی از آن به همراه سایر لایبری‌ها و یا در پروژه های موجود استفاده کرد. از سوی دیگر، ویو با استفاده از [ابزار مدرن](single-file-components.html) و [لایبری های پشتیبان](https://github.com/vuejs/awesome-vue#components--libraries) کاملا قابلیت پیاده سازی اپلیکیشن‌های پیچیده‌ تک صفحه را نیز دارد.

اگر مایلید قبل از هر چیز بیشتر با ویو آشنا شوید، ما <a id="modal-player"  href="#">یک ویدیو کوتاه ساخیتم</a> که با انجام چند پروژه نمونه به شما کمک می‌کند تا درک بهتری از مبانی هسته مرکزی این فریم ورک داشته باشید.

اگر شما یک توسعه دهنده فرانت با تجربه هستید و می‌خواهید ویو را با سایر لایبری ها و فریم ورک های فرانت اند مقایسه کنید، به صفحه [مقایسه با سایر فریم ورک‌ها](comparison.html) مراجعه کنید.


<div class="vue-mastery"><a href="https://www.vuemastery.com/courses/intro-to-vue-js/vue-instance/" target="_blank" rel="noopener" title="Free Vue.js Course">این دوره آموزشی رایگان در Vue Mastery به زبان انگلیسی به صورت مرحله به مرحله انجام یک پروژه با استفاده از ویو را آموزش می‌دهد.</a></div>

## شروع کار 

<a class="button" href="installation.html">نصب</a>

<p class="tip">در این راهنما فرض شده که شما بیشتر از حد مبتدی با HTML، CSS و JavaScript آشنایی دارید. اگر در کدنویسی فرانت‌اند کاملا  مبتدی هستید، بهتر است قبل از اینکه کار با یک فریم‌‌ورک را شروع کنید ابتدا با مفاهیم اولیه فرانت‌اند آشنا شوید و سپس به این راهنما بازگردید! آشنایی قبلی با سایر فریم‌ورک های فرانت‌اند برای درک این راهنما ضروری نبوده اما به شما کمک می‌کند تا سریعتر با مفاهیم ویو آشنا شوید.</p>

ساده‌ترین راه برای امتحان کردن ویو، استفاده از [کد Hello World در JSFiddle](https://jsfiddle.net/chrisvfritz/50wL7mdz/) است. می‌توانید آن را در یک تب جدید باز کنید و همزمان که در این راهنما به چند مثال ساده می‌پردازیم از آن استفاده کنید. و یا اینکه <a href="https://gist.githubusercontent.com/chrisvfritz/7f8d7d63000b48493c336e48b3db3e52/raw/ed60c4e5d5c6fec48b0921edaed0cb60be30e87c/index.html" target="_blank" download="index.html" rel="noopener noreferrer">یک فایل <code>index.html</code> درست کنید</a> وکد ویو را به آن وارد کنید:

``` html
<!-- برای برنامه در حال توسعه, شامل هشدارهای کمکی در کنسول -->
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
```

یا:

``` html
<!-- برای محصول نهایی ,بهینه سازی شده برای حجم فایل و سرعت -->
<script src="https://cdn.jsdelivr.net/npm/vue"></script>
```

می‌توانید در صفحه [نصب](installation.html) با گزینه‌های دیگر برای نصب ویو آشنا شوید. ما **توصیه نمی‌کنیم** که کاربران مبتدی برای نصب ویو با  `vue-cli` شروع کنند، مخصوصا اگر با <span title='Build tools'>تولید‌ابزار</span> تحت Node.js آشنایی ندارید.

اگر یک روش تعاملی را ترجیح می‌دهید، می‌توانید [این دوره آموزشی به زبان انگلیسی را در Scrimba](https://scrimba.com/playlist/pXKqta) امتحان کنید که به صورت ویدیوهای ضبط شده در محیطی تعاملی بوده که هر لحظه می‌توانید ویدیو را متوقف کنید، کدها را ویرایش کنید و نتیجه تغییرات را در همان محیط ببینید.

## <span title='Declarative Rendering'>نمایش اعلامی</span>

<div class="scrimba"><a href="https://scrimba.com/p/pXKqta/cQ3QVcr" target="_blank" rel="noopener noreferrer">این درس تعاملی را در Scrimba به زبان انگلیسی ببینید.</a></div>

سیستم هسته مرکزی Vue.js به ما این امکان را می‌دهد که با استفاده از سینتکس‌های قالب سر راست، داده را به صورت اعلامی در میان ‌تگ‌های مدل سند خروجی (DOM) نمایش دهیم.

``` html
<div id="app">
  {{ message }}
</div>
```
``` js
var app = new Vue({
  el: '#app',
  data: {
    message: 'سلام ویو!'
  }
})
```
{% raw %}
<div id="app" class="demo">
  {{ message }}
</div>
<script>
var app = new Vue({
  el: '#app',
  data: {
    message: 'سلام ویو!'
  }
})
</script>
{% endraw %}

به همین سادگی اولین اپلیکیشن ویوی خودمان را ساختیم! در ظاهر به نظر می‌آید که فقط یک <span title='string template'>قالب رشته‌ای</span> را نمایش داده ایم، اما ویو در پشت پرده خیلی کارها انجام داده. اکنون یک پیوند میان داده و <span title='DOM'>مدل سند خروجی</span> ایجاد شده و حالا همگی **<span title='reactive'>واکنش‌ دهنده</span>** هستند. از کجا می‌دانیم؟ کنسول جاوا اسکریپت مرورگرتان را (همین الان، در همین صفحه) باز کنید و متغییر `app.message` را تغییر دهید. می‌بینید که خروجی نمایش داده شده در مثال بالا نیز هماهنگ با تغییرات شما تغییر خواهد کرد.

به غیر از درج متن در محتوای درونی عناصر صفحه، همچنین می‌توانیم <span title='element attributes'>مشخصه‌ی تگ‌های</span> صفحه را به متغییرهای اپلیکیشن ویو متصل کرد:

``` html
<div id="app-2">
  <span v-bind:title="message">
    نشانه‌گر موس را برای چند ثانیه روی این متن نگاه دارید تا عنوانی که بصورت پویا به آن وصل شده را ببینید!
  </span>
</div>
```
``` js
var app2 = new Vue({
  el: '#app-2',
  data: {
    message: 'شما این صفحه را در ' + new Date().toLocaleString('fa') + ' باز کردید.'
  }
})
```
{% raw %}
<div id="app-2" class="demo">
  <span v-bind:title="message">
    نشانه‌گر موس را برای چند ثانیه روی این متن نگاه دارید تا عنوانی که بصورت پویا به آن وصل شده را ببینید!
  </span>
</div>
<script>
var app2 = new Vue({
  el: '#app-2',
  data: {
    message: 'شما این صفحه را در ' + new Date().toLocaleString('fa') + ' باز کردید.'
  }
})
</script>
{% endraw %}

در اینجا با یک پدیده جدید مواجه هستیم. ‌مشخصه `v-bind` که می‌بینید، یک  **مشخصه دستوری (directive)** است. مشخصه‌های دستوری با پیشوند  `v-` شروع می‌شوند که نشان می‌دهد آنها مشخصه‌هایی خاص و منحصر به ویو هستند و همانطور که ممکن است حدس زده باشید، آنها واکنش‌های خاصی را به سند خروجی اضافه ‌می‌کنند. در این مثال دستورالعمل می‌گوید مقدار مشخصه `title` این تگ را با متغییر `message` اپلیکیشن ویو به‌روز  نگه دار.

اگر مجددا کنسول جاوا اسکریپت مرورگر خود را باز کنید و دستور `app2.message = 'یک پیام جدید'` را وارد کنید, خواهید دید که مشخصه عنوان خروجی بالا نیز خواهد تغییر خواهد کرد.

## دستورات شرطی و حلقه‌ها

<div class="scrimba"><a href="https://scrimba.com/p/pXKqta/cEQe4SJ" target="_blank" rel="noopener noreferrer">این درس تعاملی به زبان انگلیسی را در Scrimba امتحان کنید</a></div>

همچنین به راحتی ‌میتوان وجود یا عدم وجود یک عنصر در مدل صفحه خروجی را کنترل کرد :

``` html
<div id="app-3">
  <span v-if="seen">تا شرط متغییر ‌‌seen برقرار باشد من دیده می‌شوم</span>
</div>
```

``` js
var app3 = new Vue({
  el: '#app-3',
  data: {
    seen: true
  }
})
```

{% raw %}
<div id="app-3" class="demo">
  <span v-if="seen">تا شرط متغییر ‌‌seen برقرار باشد من دیده می‌شوم</span>
</div>
<script>
var app3 = new Vue({
  el: '#app-3',
  data: {
    seen: true
  }
})
</script>
{% endraw %}

اگر در کنسول مرورگر دستور `app3.seen = false` را وارد کنید، پیام نمایش داده شده در خروجی بالا از صفحه حذف خواهد شد.

این مثال نشان می‌دهد که علاوه بر متن داخلی و مشخه‌های عناصر سند،‌ ما همچنین می‌توانیم <span title='DOM Structure'>**ساختار** مدل سند خروجی</span> را به داده های اپلیکشن ویو متصل کنیم. علاوه بر این، ویو همچنین سیستم افکت قدرتمندی را نیز ارائه می‌دهد که می‌توانید از آن برای [افکت های انتقالی](transitions.html) در هنگام درج، به روز رسانی و یا حذف عناصر سند از طریق ویو استفاده کنید.

ویو چند عدد مشخصه دستوری دیگر نیز دارد که هر کدام از آنها کارایی منحصر به خود دارند. به عنوان مثال،‌ می‌توانیم از مشخصه دستوری `v-for` برای نمایش یک لیست با استفاده از داده‌های یک متغییر آرایه استفاده کنیم:

``` html
<div id="app-4">
  <ol>
    <li v-for="todo in todos">
      {{ todo.text }}
    </li>
  </ol>
</div>
```
``` js
var app4 = new Vue({
  el: '#app-4',
  data: {
    todos: [
      { text: 'یادگیری جاوا اسکریپت' },
      { text: 'یادگیری ویو' },
      { text: 'نوشتن یک کد باحال!' }
    ]
  }
})
```
{% raw %}
<div id="app-4" class="demo">
  <ol>
    <li v-for="todo in todos">
      {{ todo.text }}
    </li>
  </ol>
</div>
<script>
var app4 = new Vue({
  el: '#app-4',
  data: {
    todos: [
      { text: 'یادگیری جاوا اسکریپت' },
      { text: 'یادگیری Vue' },
      { text: 'نوشتن یک کد باحال!' }
    ]
  }
})
</script>
{% endraw %}

دستور `app4.todos.push({ text: 'انتشار کد متن‌باز' })` را در کنسول مرورگر وارد کنید. متن جدید به لیست خروجی بالا اضافه خواهد شد.

## اداره ورودی‌ کاربر

<div class="scrimba"><a href="https://scrimba.com/p/pXKqta/czPNaUr" target="_blank" rel="noopener noreferrer">این درس تعاملی به زبان انگلیسی را در Scrimba امتحان کنید</a></div>

برای اینکه به کاربران امکان برقراری تعامل با اپلیکیشنمان را بدهیم، می‌توانیم از مشخصه دستوری `v-on` استفاده کینم تا رویداد خاصی را  تحت نظر گرفته و با وقوع آن یک تابع (method) را در اپلیکیشن ویو فرا‌خوانی کنیم:

``` html
<div id="app-5">
  <p>{{ message }}</p>
  <button v-on:click="reverseMessage">متن را برعکس کن</button>
</div>
```
``` js
var app5 = new Vue({
  el: '#app-5',
  data: {
    message: 'بابک'
  },
  methods: {
    reverseMessage: function () {
      this.message = this.message.split('').reverse().join('')
    }
  }
})
```
{% raw %}
<div id="app-5" class="demo">
  <p>{{ message }}</p>
  <button v-on:click="reverseMessage">متن را برعکس کن</button>
</div>
<script>
var app5 = new Vue({
  el: '#app-5',
  data: {
    message: 'بابک'
  },
  methods: {
    reverseMessage: function () {
      this.message = this.message.split('').reverse().join('')
    }
  }
})
</script>
{% endraw %}

توجه کنید که در کد این تابع ما بدون اینکه به <span title='DOM'>مدل سند خروجی</span> هیچ دستی بزنیم، تنها موقعیت داده‌ها (state) اپلیکیشنمان را بروزرسانی می‌کنیم و تمامی تغییرات <span title='DOM'>در مدل سند خروجی</span> خود به خود توسط ویو انجام می‌شود و کد شما تنها روی استدلال پایه اپلیکیشن متمرکز است.

ویو همچنین مشخصه دستوری `v-model` را برای ما مهیا کرده است، که با استفاده از آن می‌توان به سادگی آب خوردن، پیوندی دو طرفه میان ورودی کاربر و <span title='state'>موقعیت داده‌های</span> اپلیکیشن برقرار کرد:

``` html
<div id="app-6">
  <p>{{ message }}</p>
  <input v-model="message">
</div>
```
``` js
var app6 = new Vue({
  el: '#app-6',
  data: {
    message: 'سلام ویو!'
  }
})
```
{% raw %}
<div id="app-6" class="demo">
  <p>{{ message }}</p>
  <input v-model="message">
</div>
<script>
var app6 = new Vue({
  el: '#app-6',
  data: {
    message: 'سلام ویو!'
  }
})
</script>
{% endraw %}

## ترکیب <span title='Components'>قطعه‌کد‌ها</span> 

<div class="scrimba"><a href="https://scrimba.com/p/pXKqta/cEQVkA3" target="_blank" rel="noopener noreferrer">این درس تعاملی به زبان انگلیسی را در Scrimba امتحان کنید</a></div>

سیستم قطعه‌کد (component system) یکی دیگر از مفاهیم با اهمیت در ویو است، چرا که به ما این امکان را می‌دهد که با ترکیب قطعه کدهایی کوچک و مستقل، اپلیکیشن‌هایی در مقیاس بزرگ درست کنیم. این قطعه کدها معمولا هدف و کارایی منحصر به خود داشته و امکان استفاده مجدد از آنها در بخش های مختلف یک اپلیکیشن و حتی پروژه های دیگر وجود دارد. اگر خوب در این مورد فکر کنیم، تقریبا واسط کاربری هر اپلیکیشن را می‌توان در یک گراف درختی از قطعه‌کدها تصور کرد:

![Component Tree](/images/components.png)

در ویو، یک <span title='component'>قطعه کد</span> در واقع یک نمونه از شیء Vue با گزینه هایی از پیش تعریف شده می‌باشد.ثبت قطعه کدها در ویو خیلی ساده است:

``` js
// todo-item تعریف یک قطعه‌کد جدید به نام
Vue.component('todo-item', {
  template: '<li>این یک گزینه از چک لیست است</li>'
})
```

حالا می‌توانید از آن در ساخت قالب یک قطعه کد دیگر استفاده کنید:

``` html
<ol>
  <!-- todo-item ایجاد یک نمونه از قطعه کد -->
  <todo-item></todo-item>
</ol>
```

اما این قطعه کد برای همه چک لیست‌ها،‌متن یکسانی تولید می‌کند، که خیلی جالب نیست. باید از طریقی داده را از <span title='parent scope'>گستره قطعه کد والد</span> به <span title='child scope'>گستره قطعه کد فرزند</span> منتقل کنیم، برای این کار قطعه‌کد را ویرایش می‌کنیم تا یک [مشخصه (prop)](components.html#Props) بپذیرد:

``` js
Vue.component('todo-item', {
  //  قطعه کد گزینه چک لیست حالا یک مشخصه 
  // می‌پذیرد, که منحصر به این قطعه کد می‌باشد "prop".
  // نام دارد todo این مشخصه.
  props: ['todo'],
  template: '<li>{{ todo.text }}</li>'
})
```

حالا می‌توانیم با استفاده از مشخصه دستوری `v-bind` داده های چک لیست را در هنگام استفاده از قطعه‌کد به مشخصه `todo` آن منتقل کرد:

``` html
<div id="app-7">
  <ol>
    <!--
      ایtodo حالا ما برای هریک از گزینه های چک‌ لیست، شیء
      که نمایش می‌دهد را فراهم کرده ایم که محتوای آن می‌تواند پویا باشد
      نیز مشخص کنیم "key" ما همچنین باید برای هر قطعه کد یک کلید
      که بعدا بیشتر در این مورد توضیح خواهیم داد 
    -->
    <todo-item
      v-for="item in groceryList"
      v-bind:todo="item"
      v-bind:key="item.id"
    ></todo-item>
  </ol>
</div>
```
``` js
Vue.component('todo-item', {
  props: ['todo'],
  template: '<li>{{ todo.text }}</li>'
})

var app7 = new Vue({
  el: '#app-7',
  data: {
    groceryList: [
      { id: 0, text: 'سبزیجات' },
      { id: 1, text: 'پنیر' },
      { id: 2, text: 'هر جیز دیگه‌ای که آدما می‌خورند!' }
    ]
  }
})
```
{% raw %}
<div id="app-7" class="demo">
  <ol>
    <todo-item v-for="item in groceryList" v-bind:todo="item" :key="item.id"></todo-item>
  </ol>
</div>
<script>
Vue.component('todo-item', {
  props: ['todo'],
  template: '<li>{{ todo.text }}</li>'
})
var app7 = new Vue({
  el: '#app-7',
  data: {
    groceryList: [
      { id: 0, text: 'سبزیجات' },
      { id: 1, text: 'پنیر' },
      { id: 2, text: 'هر جیز دیگه‌ای که آدما می‌خورند!' }
    ]
  }
})
</script>
{% endraw %}

این یک مثال ساختگی بود، اما ما موفق شدیم که اپلیکیشنمان را به دو بخش کوچکتر تقسیم کنیم و قطعه کد فرزند به صورت قابل قبولی با استفاده از واسطه مشخصه‌ها (props) از قطعه‌کد والد جداسازی شده است. ما می‌توانیم فطعه کد `<todo-item>` را با منطق و قالبی پیچیده‌تر توسعه دهیم بدون اینکه کاری با اپلیکیشن والد داشته باشیم.

در اپلیکیشن‌های بزرگ لازم است که حتما آن‌ها را به قطعه‌کد‌های کوچک‌‌تر تقسیم کنیم تا فرایند توسعه اپلیکیشن قابل مدیریت باشد. [بعدا در این راهنما](components.html) خیلی بیشتر در مورد ‌<span title='components'>قطعه‌کدها</span> توضیح خواهیم داد، اما در اینجایک مثال تخیلی را آورده‌ایم که ببینید قالب یک اپلیکیشن با قطعه کدهای مختلف به چه شکل خواهد بود:

``` html
<div id="app">
  <app-nav></app-nav>
  <app-view>
    <app-sidebar></app-sidebar>
    <app-content></app-content>
  </app-view>
</div>
```

### شباهت با <span title='Custom Elements'>تگ سفارشی</span>

ممکن است متوجه شده باشید که قطعه‌کدهای ویو خیلی شبیه به **تگ‌های سفارشی (Custom Elements)** تعریف شده در [Web Components Spec](https://www.w3.org/wiki/WebComponents/) هستند. این به این دلیل است که قطعه‌کدهای ویو تا حدودی با توجه به این تعاریف طراحی شده ‌اند. برای مثال در قطعه‌کدهای ویو [Slot API](https://github.com/w3c/webcomponents/blob/gh-pages/proposals/Slots-Proposal.md) و مشخصه مخصوص `is` پیاده سازی شده است. اما چند تفاوت کلیدی نیز وجود دارد:

<<<<<<< HEAD
1. تعاریف Web Components Spec نهایی شده‌اند، اما هنوز در همه مرورگرها پشتیبانی نمی‌شوند. Safari 10.1+، Chrome 54+ و Firefox 63+ از آنها پشیتبانی می‌کنند. در مقابل، قطعه‌کدهای ویو برای اجرا به هیچ‌گونه افزونه اضافی در مرورگر نیاز نداشته و به خوبی در همه مرورگر‌های پشتیبانی شده (IE9 و بالاتر)‌ کار می‌کنند. در صورت نیاز قطعه‌کدهای ویو را می‌توان همچنین درون تگ‌های سفارشی نیز قرار داد.
=======
1. تعاریف Web Components Spec نهایی شده‌اند، اما هنوز در همه مرورگرها پشتیبانی نمی‌شوند. Safari 10.1+، Chrome 54+ و Firefox 63+ از از آنها پشیتبانی می‌کنند. در مقابل، قطعه‌کدهای ویو برای اجرا به هیچ‌گونه افزونه اضافی در مرورگر نیاز نداشته و به خوبی در همه مرورگر‌های پشتیبانی شده (IE9 و بالاتر)‌ کار می‌کنند. در صورت نیاز قطعه‌کدهای ویو را می‌توان همچنین درون تگ‌های سفارشی نیز قرار داد.
>>>>>>> ce6c8fcddb50502f15a46eae40a33fff988948df

2. قطعه‌کدهای ویو امکانات ویژه‌ای را فراهم ‌می‌کنند که در تگ‌های سفارشی وجود ندارند، به عنوان مثال جریان انتقال داده‌ها میان قطعه‌کدها، تعامل رویدادی و یکپارچگی تولیدابزار.

اگرچه ویو به صورتی داخلی از تگ‌های سفارشی استفاده نمی‌کند، وقتی که قرار باشدبه عنوان تگ سفارشی استفاده یا پخش شود از  [قابلیت هماهنگی بالایی](https://custom-elements-everywhere.com/#vue) برخوردار است. همچنین Vue CLI از ساخت قطعه‌کدهایی که خود را به عنوان تگ‌های سفارشی ثبت می‌کنند، پشتیبانی می‌کند.

## آماده‌اید که بیشتر بدانید؟

ما بطور خلاصه ابتدایی‌ترین امکانات هسته مرکزی ویو را معرفی کردیم - ادامه این راهنما بصورت جامع‌تر به توضیح این امکانات و سایر امکانات پیشرفته‌تر با جزيیات دقیق‌تر می‌پردازد، پس ادامه مطالب را از دست ندهید!

<div id="video-modal" class="modal"><div class="video-space" style="padding: 56.25% 0 0 0; position: relative;"><iframe src="https://player.vimeo.com/video/247494684" style="height: 100%; left: 0; position: absolute; top: 0; width: 100%; margin: 0" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></div><script src="https://player.vimeo.com/api/player.js"></script><p class="modal-text">Video by <a href="https://www.vuemastery.com" target="_blank" rel="noopener" title="Vue.js Courses on Vue Mastery">Vue Mastery</a>. Watch Vue Mastery’s free <a href="https://www.vuemastery.com/courses/intro-to-vue-js/vue-instance/" target="_blank" rel="noopener" title="Vue.js Courses on Vue Mastery">Intro to Vue course</a>.</div>
