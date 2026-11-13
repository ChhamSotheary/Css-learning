# Chapter 04៖ Bootstrap Grid System

## គោលបំណង
បង្កើត layout responsive ដោយ container → row → columns និងគ្រប់គ្រង gutter/column spans។

## រចនាសម្ព័ន្ធ
~~~html
<div class="container">
  <div class="row">
    <div class="col">ជួរឈរមួយ</div>
    <div class="col">ជួរឈរពីរ</div>
  </div>
</div>
~~~
Grid default មាន 12 columns, ប្រើ Flexbox។ **container** ផ្តល់ទទឹង/padding; **row** គ្រប់គ្រង gutter; **col** ឬ **col-*** ជាកូន row។ កុំដាក់ col ដោយគ្មាន row លើកលែងប្រើ layout ដែលបានកំណត់ផ្សេង។

## Column spans និង responsive tiers
~~~html
<div class="row">
  <div class="col-12 col-md-8">Main</div>
  <aside class="col-12 col-md-4">Sidebar</aside>
</div>
~~~
នៅ xs ទាំងពីរជា 100% ទទឹង; ចាប់ពី md ឡើងទៅ 8/12 និង 4/12។ **col-6** = ពាក់កណ្តាល; **col-md-4** = 4/12 ចាប់ពី md ឡើង។ អាចបញ្ចូល classes ជាច្រើនសម្រាប់ behavior តាម breakpoint។

## Auto-layout, row-cols និង gutter
~~~html
<div class="row row-cols-1 row-cols-sm-2 row-cols-lg-4 g-3">
  <div class="col"><article class="card">...</article></div>
  <div class="col"><article class="card">...</article></div>
</div>
~~~
col ដោយគ្មានលេខចែកទទឹងស្មើ; row-cols កំណត់ចំនួន columns លើ row; g-* ជា gutter ទាំងពីរអ័ក្ស; gx-* ផ្ដេក; gy-* បញ្ឈរ។ Gutters មិនមែន margin ធម្មតាទេ; row/column មាន interaction របស់វា។

## Offset/order/nesting
មាន offset និង order classes សម្រាប់កែទីតាំង/លំដាប់មើលឃើញ។ កុំប្តូរ visual order ឱ្យផ្ទុយពី reading/keyboard order។ Nested grid ដាក់ row ថ្មីក្នុង column មួយ ដើម្បីរៀបចំផ្នែកខាងក្នុង; កុំ nested លើសត្រូវការ។

## កំហុសទូទៅ
- row មិនបានរុំ columns។
- ផលបូក column spans លើស 12 ដោយចៃដន្យ (វានឹង wrap)។
- ប្រើ col-* ជា replacement សម្រាប់ semantic layout ដោយមិនសាក screen reader។
- gutter ច្រើនធ្វើឱ្យ content រុញចេញពី container។
- ប្រើ grid framework class ទាំងអស់ និង CSS grid ទាំងអស់លើ element ដូចគ្នាដោយមិនយល់ conflict។

## អនុវត្ត
បង្កើត product listing: mobile 1 column, sm 2, lg 4; gutter 1rem equivalent។ បង្កើត layout main/sidebar ដែល stack លើ mobile និង side-by-side ពី md ឡើងទៅ។

## សំណួរ
1. Bootstrap grid មានប៉ុន្មាន columns?
2. col-md-4 មានន័យអ្វី?
3. row-cols និង col-4 ខុសគ្នាត្រង់ណា?

**ចម្លើយ**៖ 12; 4/12 ពី md ឡើងទៅ; row-cols កំណត់ចំនួន columns លើ parent row ខណៈ col-4 កំណត់ span របស់ column នីមួយៗ។