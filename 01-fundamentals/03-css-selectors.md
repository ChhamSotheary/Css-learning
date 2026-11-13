# មេរៀន ៣៖ CSS Selectors

## គោលបំណង
ជ្រើស element តាម tag, class, id, ទំនាក់ទំនងក្នុង DOM និង attribute។

## Selectors មូលដ្ឋាន
~~~css
p { color: #333; }                 /* element */
.notice { background: #fff3cd; }   /* class */
#main-title { color: navy; }       /* id */
* { box-sizing: border-box; }      /* universal */
h1, h2, h3 { font-family: sans-serif; } /* grouping */
~~~
Class អាចប្រើលើ element ច្រើន; id គួរតែមានតែមួយក្នុងទំព័រ។ CSS class ចាប់ផ្តើមដោយ dot; id ចាប់ផ្តើមដោយ #។

## Combinators: ទំនាក់ទំនង element
~~~css
article p { color: #444; }   /* descendant: p នៅកន្លែងណាក៏បានក្នុង article */
.menu > li { list-style: none; } /* child ផ្ទាល់ */
h2 + p { margin-top: 0; }    /* sibling បន្ទាប់ភ្លាម */
h2 ~ p { color: #555; }      /* sibling ទាំងអស់ក្រោយ h2 */
~~~
Space, >, + និង ~ មានន័យខុសគ្នា។ ប្រើ selector សាមញ្ញគ្រប់គ្រាន់ ដើម្បីឱ្យ CSS ងាយកែ។

## Attribute selectors
~~~css
input[type="email"] { border-color: teal; }
a[target] { text-decoration: underline; }
a[href^="https"] { color: green; } /* ចាប់ផ្តើមដោយ */
a[href$=".pdf"] { font-weight: bold; } /* បញ្ចប់ដោយ */
~~~
Attribute selectors អាចត្រួតលើ attribute មាន/តម្លៃជាក់លាក់ ឬ prefix/suffix។

## Specificity សង្ខេប
Rule ច្រើនអាចត្រូវនឹង element ដូចគ្នា។ ជាទូទៅ id មាន specificity ខ្ពស់ជាង class/attribute/pseudo-class; class ខ្ពស់ជាង element។ Rule ដែលមាន specificity ស្មើគ្នា ក្រោយជាងអាចឈ្នះ។ កុំដោះស្រាយរាល់បញ្ហាដោយបន្ថែម id ឬ !important; ជ្រើស selector ដែលមានគោលបំណងច្បាស់។ ពន្យល់ពេញលេញនៅមេរៀន ២០។

## អនុវត្ត
~~~html
<article class="card">
  <h2 id="title">ផលិតផល</h2>
  <p>តម្លៃពិសេស</p>
  <a href="manual.pdf">អានសៀវភៅណែនាំ</a>
</article>
~~~
សរសេរ selector ឱ្យ h2 មានពណ៌ខៀវ, paragraph ក្នុង card មាន line-height 1.6, និង link ទៅ PDF មាន bold។

## លំហាត់
1. ជ្រើស li ដែលជាកូនផ្ទាល់របស់ ul.menu។
2. ជ្រើស p ដែលនៅក្រោយ h2 ភ្លាម។
3. តើ .card និង #card ខុសគ្នាយ៉ាងដូចម្តេច?

**ចម្លើយ**៖ ul.menu > li; h2 + p; class អាចប្រើលើច្រើន element ខណៈ id គួរតែ unique ក្នុង document។