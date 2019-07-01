---
title: Vue Instance
type: guide
order: 3
---

## ساختن یک Vue Instance 

هر اپلیکیشن ویو با ساختن یک Instance جدید از شئ ویو با استفاده از تابع `Vue` آغاز می‌شود:

```js
var vm = new Vue({
  // Options
})
```

در طراحی ویو تا حدودی از [الگوی MVVM](https://en.wikipedia.org/wiki/Model_View_ViewModel) الهام گرفته شده‌است؛ اگرچه ارتباط چندان نزدیکی ندارند. به عنوان یک قرارداد ما معمولا از متغییری به نام `vm` (خلاصه شده ViewModel) برای اشاره به Vue Instance استفاده می‌کنیم. 

زمانی که یک instance از شئ ویو می‌سازید، **یک شئ (Object) از آپشن‌ها** را به آن می‌دهید. بیشتر این راهنما به شما توضیح می‌دهند که چطور با استفاده از این آپشن‌ها رفتار مورد نظرتان را بوجود بیاورید. به عنوان مرجع می‌توانید لیست کامل این آپشن‌ها را در [مرجع API](../api/#Options-Data) مرور کنید.

یک اپلیکیشن ویو شامل یک **root Vue instance** است که با استفاده از `new Vue` ساخته شده است، می‌تواند یک ساختار تو در تو درختی از component‌های قابل استفاده مجدد، داشته باشد. به عنوان مثال ساختار درختی component‌های یک اپ todo می‌تواند به این شکل باشد:

```
Root Instance
└─ TodoList
   ├─ TodoItem
   │  ├─ DeleteTodoButton
   │  └─ EditTodoButton
   └─ TodoListFooter
      ├─ ClearTodosButton
      └─ TodoListStatistics
```

ما در مورد [سیستم componentها](components.html) بعدا با جزئیات صحبت می‌کنیم. اما در حال حاضر فقط بدانید که هر component ویو در واقع یک vue instance هم هستند و بنابراین آپشن‌های مشابهی قبول می‌کنند. (به جز تعداد کمی از آپشن‌های مخصوص root.)

## Data و Methodها

وقتی یک instance ویو ساخته می‌شود، ویو تمام propertyهای شئ `data` را به **سیستم واکنشگرایی (reactivity)** خود اضافه می‌کند. وقتی مقدار این propertyها تغییر می‌کند، صفحه «واکنش» نشان داده و متناسب با مقدار جدید بروز می‌شود.

```js
// شئ data ما
var data = { a: 1 }

// شئ به یک instance از ویو اضافه شده‌است.
var vm = new Vue({
  data: data
})


// با گرفتن یک property از instance
// همان مقدار داده اصلی را به دست می‌آوریم.
vm.a == data.a // => true


// همچنین افزودن یک property جدید به instance
// مقدار داده اصلی را تحت تاثیر قرار می‌دهد.
vm.a = 2
data.a // => 2

// ... و برعکس
data.a = 3
vm.a // => 3
```

وقتی این data تغییر می‌کند، صفحه مجددا رندر می‌شود. باید توجه داشت که propertyهای درون `data` تنها زمانی **reactive** هستند که در زمان ساخته شدن instance وجود داشته باشند. به این معنا که اگر یک property جدید اضافه کنید، مثل

```js
vm.b = 'hi'
```

تغییرات `b` منجر به بروزرسانی در صفحه نمی‌شود. اگر شما می‌دانید که یک property را در آینده نیاز خواهید داشت، اما در ابتدا مقدار آن خالیست یا وجود ندارد، شما می‌توانید برای آن یک مقدار اولیه تعیین کنید. برای مثال:

```js
data: {
  newTodoText: '',
  visitCount: 0,
  hideCompletedTodos: false,
  todos: [],
  error: null
}
```

تنها استثنا استفاده از `Object.freeze()` است، که جلوی هر گونه تغییری در proprertyها را می‌گیرد؛ به این معنی که سیستم واکنش‌گرایی (reactivity) نمی‌توند تغییرات را _دنبال_ کند.

```js
var obj = {
  foo: 'bar'
}

Object.freeze(obj)

new Vue({
  el: '#app',
  data: obj
})
```

```html
<div id="app">
  <p>{{ foo }}</p>
  <!-- این دیگر نمی‌تواند `foo` را بروزرسانی کند! -->
  <button v-on:click="foo = 'baz'">Change it</button>
</div>
```

m 
```js
var data = { a: 1 }
var vm = new Vue({
  el: '#example',
  data: data
})

vm.$data === data // => true
vm.$el === document.getElementById('example') // => true

// $watch is an instance method
vm.$watch('a', function (newValue, oldValue) {
  // This callback will be called when `vm.a` changes
})
```

در آینده برای دیدن لیست کاملی از propertyهای instance ویو و متودها، می‌توانید به [مرجع API](../api/#Instance-Properties) مراجعه کنید.

## Hookهای چرخه حیات Instance ویو

هر instance ویو پس از ساخته شدن، یک سری مراحل مقداردهی را  پشت سر می‌گذارد؛ برای مثال در ابتدا باید مقدار داده‌ها را بخواند، template را کامپایل کند، instance را در ‌DOM قرار دهد و هر زمان که داده‌ها تغییر کردند، DOM را بروزرسانی کند. در طول مسیر ویو تعدادی فانکشن به اسم **lifecycle hooks** را اجرا می‌کند و به کاربران اجازه می‌دهد تا کدهای خود را به هر کدام از این مراحل اضافه کنند.

به عنوان مثال هوک [`created`](../api/#created) می‌تواند برای اجرا کردن کد، بعد از ساخته شدن یک instance استفاده شود.

```js
new Vue({
  data: {
    a: 1
  },
  created: function () {
    // `this` به vm instance اشاره دارد.
    console.log('a is: ' + this.a)
  }
})
// => "a is: 1"
```

هوک‌های دیگری هم وجود دارند که در مراحل دیگر چرخه حیات instance اجرا می‌شوند؛ مانند [`mounted`](../api/#mounted), [`updated`](../api/#updated) و [`destroyed`](../api/#destroyed). همه هوک‌های چرخه حیات با `this` که به instance ویو خودشان اشاره دارد، صدا زده می‌شوند.

<p class="tip">هرگز از [arrow function‌ها](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Functions/Arrow_functions) در گزینه‌ها یا کال‌بک‌هایی مثل `created: () => console.log(this.a)` یا `vm.$watch('a', newValue => this.myMethod())` استفاده نکنید. از آنجایی که arrow function‌ها `this` ندارند، `this` مانند هر متغییر دیگری در لایه‌های بالاتر اسکوپ جستجو می‌شود؛ تا زمانی که مقداری برایش پیدا شود. البته اغلب به خطاهای `Uncaught TypeError: Cannot read property of undefined` یا `Uncaught TypeError: this.myMethod is not a function` می‌انجامد.</p>

## نمودار چرخه عمر

در پایین یک نمودار از چرخه حیات instance را می‌بینید. در حال حاضر نیازی نیست به طور کامل این نمودار را درک کنید، اما به مرور با یادگیری و تمرین بیشتر این تصویر می‌تواند یک مرجع کار‌آمد باشد.

![چرخه حیات instance ویو](/images/lifecycle.png)
