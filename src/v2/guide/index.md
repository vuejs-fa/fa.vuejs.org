---
title: مقدمه
type: guide
order: 2
---

## ویو.جی اس چیست؟


ویو یک **فریم ورک تکاملی** جاوا اسکریپت برای تولید واسط کاربری تحت وب است. برخلاف فریم ورک‌های یکپارچه، ویو از پایه به گونه‌ای طراحی شده است که با توجه به نیاز برنامه، مرحله به مرحله قابل تطبیق باشد. هسته مرکزی لایبری فقط روی بخش نما (view) متمرکز است و می‌توان به راحتی از آن به همراه سایر لایبری‌ها و یا در پروژه های موجود استفاده کرد. از سوی دیگر، ویو با استفاده از [ابزار مدرن](single-file-components.html) و [لایبری های پشتیبان](https://github.com/vuejs/awesome-vue#components--libraries) کاملا ظرفیت پیاده سازی اپلیکیشن‌های پیچیده‌ تک صفحه را نیز دارد.

اگر مایلید قبل از هر چیز بیشتر با ویو آشنا شوید، ما <a id="modal-player"  href="#">یک ویدیو کوتاه ساخیتم</a> که با انجام چند پروژه نمونه به شما کمک می‌کند تا درک بهتری از مبانی هسته مرکزی این فریم ورک داشته باشید.

اگر شما یک فرانت‌اند دولپر با تجربه هستید و می‌خواهید ویو را با سایر لایبری ها و فریم ورک های فرانت اند مقایسه کنید، به صفحه [مقایسه با سایر فریم ورک‌ها](comparison.html) مراجعه کنید.


<div class="vue-mastery"><a href="https://www.vuemastery.com/courses/intro-to-vue-js/vue-instance/" target="_blank" rel="noopener" title="Free Vue.js Course">این دوره آموزشی رایگان در Vue Mastery به زبان انگلیسی به صورت مرحله به مرحله انجام یک پروژه با استفاده از ویو را آموزش می‌دهد.</a></div>

## شروع کار 

<a class="button" href="installation.html">نصب</a>

<p class="tip">در این راهنما فرض شده که آشنایی شما با HTML، CSS و JavaScript بیشتر از حد مبتدی است. اگر در کدنویسی فرانت‌اند کاملا  مبتدی هستید، بهتر است قبل از اینکه کار با یک فریم‌‌ورک را شروع کنید ابتدا با مفاهیم اولیه فرانت‌اند آشنا شوید و سپس به این راهنما بازگردید! آشنایی قبلی با سایر فریم‌ورک های فرانت‌اند برای درک این راهنما ضروری نبوده اما به شما کمک می‌کند تا سریعتر با مفاهیم ویو آشنا شوید.</p>

ساده‌ترین راه برای امتحان کردن Vue.js، استفاده از [کد Hello World در JSFiddle](https://jsfiddle.net/chrisvfritz/50wL7mdz/) است. می‌توانید آن را در یک تب جدید باز کنید و همزمان که در این راهنما به چند مثال ساده می‌پردازیم از آن استفاده کنید. و یا اینکه <a href="https://gist.githubusercontent.com/chrisvfritz/7f8d7d63000b48493c336e48b3db3e52/raw/ed60c4e5d5c6fec48b0921edaed0cb60be30e87c/index.html" target="_blank" download="index.html" rel="noopener noreferrer">یک فایل <code>index.html</code> درست کنید</a> و کد ویو را در آن وارد کنید:

``` html
<!-- برای برنامه در حال توسعه, شامل هشدارهای کمکی در کنسول -->
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
```

یا:

``` html
<!-- برای محصول نهایی ,بهینه سازی شده برای حجم فایل و سرعت -->
<script src="https://cdn.jsdelivr.net/npm/vue"></script>
```

می‌توانید در صفحه [نصب](installation.html) با گزینه‌های دیگر برای نصب ویو آشنا شوید. ما **توصیه نمی‌کنیم** که کاربران مبتدی برای نصب ویو با  `vue-cli` شروع کنند، مخصوصا اگر با تولید ابزار تحت Node.js آشنایی ندارید.

اگر یک روش تعاملی را ترجیح می‌دهید، می‌توانید [این سری آموزشی به زبان انگلیسی را در Scrimba](https://scrimba.com/playlist/pXKqta) امتحان کنید که به صورت ویدوهای ضبط شده در محیطی تعاملی بوده که هر لحظه می‌توانید ویدیو را متوقف کنید، کدها را ویرایش کند و نتیجه تغییرات را در همان محیط ببینید.

## نمایش اعلامی

<div class="scrimba"><a href="https://scrimba.com/p/pXKqta/cQ3QVcr" target="_blank" rel="noopener noreferrer">این را در Scrimba به زبان انگلیسی ببینید.</a></div>

سیستم هسته مرکزی Vue.js به ما این امکان را می‌دهد که با استفاده از سینتکس های قالب سر راست، داده را به صورت اعلامی در میان ‌تگ‌های نمای خروجی نمایش دهیم.

``` html
<div id="app">
  {{ message }}
</div>
```
``` js
var app = new Vue({
  el: '#app',
  data: {
    message: 'Hello Vue!'
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
    message: 'Hello Vue!'
  }
})
</script>
{% endraw %}

به همین سادگی اولین اپلیکیشن ویوی خودمون را ساختیم! در ظاهر به نظر میاد که فقط یک قالب رشته‌ای را نمایش دادیم، اما ویو پشت پرده خیلی کارها انجام داده. اکنون یک پیوند میان داده و مدل سند خروجی ایجاد شده و حالا همگی **واکنش‌ دهنده** هستند. از کجا میدونیم؟ کنسول جاوا اسکریپت مرورگرتون را (همین الان، توی همین صفحه) باز کنید و متغییر `app.message` را تغییر بدهید. می‌بینید که خروجی نمایش داده شده در مثال بالا نیز هماهنگ با تغییرات شما تغییر خواهد کرد.

In addition to text interpolation, we can also bind element attributes like this:

``` html
<div id="app-2">
  <span v-bind:title="message">
    Hover your mouse over me for a few seconds
    to see my dynamically bound title!
  </span>
</div>
```
``` js
var app2 = new Vue({
  el: '#app-2',
  data: {
    message: 'You loaded this page on ' + new Date().toLocaleString()
  }
})
```
{% raw %}
<div id="app-2" class="demo">
  <span v-bind:title="message">
    Hover your mouse over me for a few seconds to see my dynamically bound title!
  </span>
</div>
<script>
var app2 = new Vue({
  el: '#app-2',
  data: {
    message: 'You loaded this page on ' + new Date().toLocaleString()
  }
})
</script>
{% endraw %}

Here we are encountering something new. The `v-bind` attribute you are seeing is called a **directive**. Directives are prefixed with `v-` to indicate that they are special attributes provided by Vue, and as you may have guessed, they apply special reactive behavior to the rendered DOM. Here, it is basically saying "keep this element's `title` attribute up-to-date with the `message` property on the Vue instance."

If you open up your JavaScript console again and enter `app2.message = 'some new message'`, you'll once again see that the bound HTML - in this case the `title` attribute - has been updated.

## Conditionals and Loops

<div class="scrimba"><a href="https://scrimba.com/p/pXKqta/cEQe4SJ" target="_blank" rel="noopener noreferrer">Try this lesson on Scrimba</a></div>

It's easy to toggle the presence of an element, too:

``` html
<div id="app-3">
  <span v-if="seen">Now you see me</span>
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
  <span v-if="seen">Now you see me</span>
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

Go ahead and enter `app3.seen = false` in the console. You should see the message disappear.

This example demonstrates that we can bind data to not only text and attributes, but also the **structure** of the DOM. Moreover, Vue also provides a powerful transition effect system that can automatically apply [transition effects](transitions.html) when elements are inserted/updated/removed by Vue.

There are quite a few other directives, each with its own special functionality. For example, the `v-for` directive can be used for displaying a list of items using the data from an Array:

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
      { text: 'Learn JavaScript' },
      { text: 'Learn Vue' },
      { text: 'Build something awesome' }
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
      { text: 'Learn JavaScript' },
      { text: 'Learn Vue' },
      { text: 'Build something awesome' }
    ]
  }
})
</script>
{% endraw %}

In the console, enter `app4.todos.push({ text: 'New item' })`. You should see a new item appended to the list.

## Handling User Input

<div class="scrimba"><a href="https://scrimba.com/p/pXKqta/czPNaUr" target="_blank" rel="noopener noreferrer">Try this lesson on Scrimba</a></div>

To let users interact with your app, we can use the `v-on` directive to attach event listeners that invoke methods on our Vue instances:

``` html
<div id="app-5">
  <p>{{ message }}</p>
  <button v-on:click="reverseMessage">Reverse Message</button>
</div>
```
``` js
var app5 = new Vue({
  el: '#app-5',
  data: {
    message: 'Hello Vue.js!'
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
  <button v-on:click="reverseMessage">Reverse Message</button>
</div>
<script>
var app5 = new Vue({
  el: '#app-5',
  data: {
    message: 'Hello Vue.js!'
  },
  methods: {
    reverseMessage: function () {
      this.message = this.message.split('').reverse().join('')
    }
  }
})
</script>
{% endraw %}

Note that in this method we update the state of our app without touching the DOM - all DOM manipulations are handled by Vue, and the code you write is focused on the underlying logic.

Vue also provides the `v-model` directive that makes two-way binding between form input and app state a breeze:

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
    message: 'Hello Vue!'
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
    message: 'Hello Vue!'
  }
})
</script>
{% endraw %}

## Composing with Components

<div class="scrimba"><a href="https://scrimba.com/p/pXKqta/cEQVkA3" target="_blank" rel="noopener noreferrer">Try this lesson on Scrimba</a></div>

The component system is another important concept in Vue, because it's an abstraction that allows us to build large-scale applications composed of small, self-contained, and often reusable components. If we think about it, almost any type of application interface can be abstracted into a tree of components:

![Component Tree](/images/components.png)

In Vue, a component is essentially a Vue instance with pre-defined options. Registering a component in Vue is straightforward:

``` js
// Define a new component called todo-item
Vue.component('todo-item', {
  template: '<li>This is a todo</li>'
})
```

Now you can compose it in another component's template:

``` html
<ol>
  <!-- Create an instance of the todo-item component -->
  <todo-item></todo-item>
</ol>
```

But this would render the same text for every todo, which is not super interesting. We should be able to pass data from the parent scope into child components. Let's modify the component definition to make it accept a [prop](components.html#Props):

``` js
Vue.component('todo-item', {
  // The todo-item component now accepts a
  // "prop", which is like a custom attribute.
  // This prop is called todo.
  props: ['todo'],
  template: '<li>{{ todo.text }}</li>'
})
```

Now we can pass the todo into each repeated component using `v-bind`:

``` html
<div id="app-7">
  <ol>
    <!--
      Now we provide each todo-item with the todo object
      it's representing, so that its content can be dynamic.
      We also need to provide each component with a "key",
      which will be explained later.
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
      { id: 0, text: 'Vegetables' },
      { id: 1, text: 'Cheese' },
      { id: 2, text: 'Whatever else humans are supposed to eat' }
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
      { id: 0, text: 'Vegetables' },
      { id: 1, text: 'Cheese' },
      { id: 2, text: 'Whatever else humans are supposed to eat' }
    ]
  }
})
</script>
{% endraw %}

This is a contrived example, but we have managed to separate our app into two smaller units, and the child is reasonably well-decoupled from the parent via the props interface. We can now further improve our `<todo-item>` component with more complex template and logic without affecting the parent app.

In a large application, it is necessary to divide the whole app into components to make development manageable. We will talk a lot more about components [later in the guide](components.html), but here's an (imaginary) example of what an app's template might look like with components:

``` html
<div id="app">
  <app-nav></app-nav>
  <app-view>
    <app-sidebar></app-sidebar>
    <app-content></app-content>
  </app-view>
</div>
```

### Relation to Custom Elements

You may have noticed that Vue components are very similar to **Custom Elements**, which are part of the [Web Components Spec](https://www.w3.org/wiki/WebComponents/). That's because Vue's component syntax is loosely modeled after the spec. For example, Vue components implement the [Slot API](https://github.com/w3c/webcomponents/blob/gh-pages/proposals/Slots-Proposal.md) and the `is` special attribute. However, there are a few key differences:

1. The Web Components Spec has been finalized, but is not natively implemented in every browser. Safari 10.1+, Chrome 54+ and Firefox 63+ natively support web components. In comparison, Vue components don't require any polyfills and work consistently in all supported browsers (IE9 and above). When needed, Vue components can also be wrapped inside a native custom element.

2. Vue components provide important features that are not available in plain custom elements, most notably cross-component data flow, custom event communication and build tool integrations.

Although Vue doesn't use custom elements internally, it has [great interoperability](https://custom-elements-everywhere.com/#vue) when it comes to consuming or distributing as custom elements. Vue CLI also supports building Vue components that register themselves as native custom elements.

## Ready for More?

We've briefly introduced the most basic features of Vue.js core - the rest of this guide will cover them and other advanced features with much finer details, so make sure to read through it all!

<div id="video-modal" class="modal"><div class="video-space" style="padding: 56.25% 0 0 0; position: relative;"><iframe src="https://player.vimeo.com/video/247494684" style="height: 100%; left: 0; position: absolute; top: 0; width: 100%; margin: 0" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></div><script src="https://player.vimeo.com/api/player.js"></script><p class="modal-text">Video by <a href="https://www.vuemastery.com" target="_blank" rel="noopener" title="Vue.js Courses on Vue Mastery">Vue Mastery</a>. Watch Vue Mastery’s free <a href="https://www.vuemastery.com/courses/intro-to-vue-js/vue-instance/" target="_blank" rel="noopener" title="Vue.js Courses on Vue Mastery">Intro to Vue course</a>.</div>
