# មេរៀន ១២៖ CSS Grid

## គោលបំណង
បង្កើត layout ពីរវិមាត្រ ដោយកំណត់ columns/rows, areas និង responsive tracks។

## ចាប់ផ្តើម
~~~css
.gallery {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 1rem;
}
~~~
Grid container ជា parent; grid items ជាកូនផ្ទាល់។ **fr** គឺចំណែកកន្លែងទំនេរ បន្ទាប់ពី fixed/auto tracks គិតរួច។ **gap** កំណត់ចន្លោះរវាង tracks។

## Repeat, minmax, auto-fit
~~~css
.cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(min(100%, 15rem), 1fr));
  gap: 1rem;
}
~~~
minmax(min,max) កំណត់ track ទាប/ខ្ពស់។ auto-fit បង្រួម tracks ទទេឱ្យអាចពង្រីក tracks មាន content; auto-fill រក្សាទុក tracks ទទេក្នុងការរៀបចំ។ ជម្រើសទាំងពីរបង្កើត layout បត់បែនដោយមិនចាំបាច់ media query សម្រាប់គ្រប់ទំហំ។

## Grid lines និង span
~~~css
.featured { grid-column: 1 / span 2; }
~~~
Track lines ជាលេខបំបែកជួរឈរ/ជួរដេក។ span 2 មានន័យថាឆ្លងកាត់ពីរ tracks។ កុំកំណត់ item position តាមលេខច្រើនពេក បើ layout ត្រូវ responsive; ពិនិត្យ overlap។

## Template areas
~~~css
.page {
  display: grid;
  grid-template-columns: 15rem 1fr;
  grid-template-areas: "side main";
  gap: 1rem;
}
.sidebar { grid-area: side; }
.content { grid-area: main; }
@media (max-width: 45rem) {
  .page { grid-template-columns: 1fr; grid-template-areas: "main" "side"; }
}
~~~
Areas ធ្វើឱ្យ layout អានងាយ។ កុំរៀប DOM ឱ្យខុស semantic តែដើម្បីឱ្យមើលស្អាត; លំដាប់ DOM មានសារៈសំខាន់សម្រាប់ keyboard/screen reader។

## Nested Grid
កូន element អាចជា grid container ផ្ទាល់ ដើម្បីរៀបកូនរបស់វា។ ប្រើ nested grid នៅពេលផ្នែកខាងក្នុងត្រូវការរចនាសម្ព័ន្ធដាច់ដោយឡែក។

## អនុវត្ត
បង្កើត product grid ដែលមាន card 4+ items ប្រើ repeat(auto-fit, minmax(...))។ បង្កើត dashboard areas: header, sidebar, main, footer ហើយកែ mobile layout។

## លំហាត់
1. fr មានតួនាទីអ្វី?
2. minmax(15rem,1fr) មានន័យដូចម្តេច?
3. Grid ខុសពី Flexbox ត្រង់ណា?

**ចម្លើយ**៖ fr ចែក free space; track យ៉ាងតិច 15rem ហើយអាចពង្រីកយកកន្លែងទំនេរ; Grid គ្រប់គ្រងជួរដេក/ជួរឈរពីរវិមាត្រ ខណៈ Flexbox ផ្តោតមួយអ័ក្ស (ទោះអាច wrap បានក៏ដោយ)។