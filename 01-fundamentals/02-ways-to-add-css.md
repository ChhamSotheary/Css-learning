# មេរៀន ២៖ វិធីដាក់ CSS ក្នុងទំព័រ

## គោលបំណង
ស្គាល់ inline, internal និង external CSS; ជ្រើសរើសរបៀបត្រឹមត្រូវ និងរៀបចំឯកសារឱ្យងាយថែទាំ។

## ១. Inline CSS
សរសេរ style attribute លើ element ផ្ទាល់៖
~~~html
<p style="color: teal;">អត្ថបទពណ៌បៃតងខៀវ</p>
~~~
ប្រើសម្រាប់សាកល្បងលឿន ឬ style តែមួយករណី។ មិនសមស្របសម្រាប់គេហទំព័រធំ ព្រោះពិបាកប្រើឡើងវិញ និង HTML ច្របូកច្របល់។

## ២. Internal CSS
សរសេរ rule ក្នុង element style នៅ head៖
~~~html
<head>
  <style>
    body { font-family: sans-serif; }
  </style>
</head>
~~~
សមស្របសម្រាប់ឯកសារ demo តែមួយ; ទំព័រច្រើននឹងចម្លង CSS ដដែលៗ។

## ៣. External CSS (ណែនាំសម្រាប់គម្រោង)
បង្កើត style.css ហើយភ្ជាប់ក្នុង head៖
~~~html
<head>
  <link rel="stylesheet" href="css/style.css">
</head>
~~~
~~~css
/* css/style.css */
body {
  font-family: sans-serif;
}
~~~
ផ្លូវ href គិតពីទីតាំង HTML។ ប្រសិនបើ style.css នៅជិត HTML ប្រើ **href="style.css"**។ ពិនិត្យឈ្មោះអក្សរតូច/ធំ ព្រោះ server Linux អាចប្រកាន់ case។

## រចនាសម្ព័ន្ធសាមញ្ញ
~~~text
my-site/
├── index.html
└── css/
    └── style.css
~~~

## Best practices
- ប្រើ external CSS សម្រាប់គម្រោង និងចែក rule តាមគោលបំណង មិនមែនតាមគ្រប់ component តូចៗទេ។
- ប្រើឈ្មោះឯកសារ/ថតច្បាស់។
- កុំប្រើ inline style ជំនួស stylesheet ទាំងមូល។
- បើមាន stylesheet ច្រើន កំណត់លំដាប់ភ្ជាប់ដោយចេតនា ព្រោះ cascade អាចធ្វើឱ្យ rule ក្រោយ override rule មុន។
- ប្រើ browser DevTools ដើម្បីពិនិត្យថា stylesheet ត្រូវបាន load និង rule ណាឈ្នះ។

## លំហាត់អនុវត្ត
បង្កើត index.html និង css/style.css។ ដាក់ h1 និង card មួយ។ ភ្ជាប់ stylesheet, កំណត់ background body និងពណ៌ card។ សាកដក href ចេញដើម្បីសង្កេតភាពខុសគ្នា រួចដាក់វិញ។

## ពិនិត្យខ្លួនឯង
1. តើរបៀបណាងាយ reuse លើទំព័រច្រើន?
2. ហេតុអ្វី inline CSS ពិបាកថែទាំ?
3. បើ CSS មិនអនុវត្ត តើត្រូវពិនិត្យអ្វីមុន?

**ចម្លើយ**៖ External CSS; ព្រោះ style ច្របូក HTML និងចម្លងពិបាក; ពិនិត្យ href/ផ្លូវឯកសារ, DevTools Network និង syntax error។