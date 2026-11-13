# Chapter 13៖ Helpers, Utilities និង Utility API

## Helpers
Helpers ជា class សម្រាប់ use case ជាក់លាក់ដែលលើសពី utility property សាមញ្ញ៖ visually-hidden, stretched-link, ratio, position, focus-ring និង color modes helpers (អាស្រ័យ version)។ ឧទាហរណ៍ visually-hidden បិទមាតិកាពីការមើល ប៉ុន្តែរក្សាសម្រាប់ assistive technology; visually-hidden-focusable បង្ហាញវិញពេល focus។

~~~html
<a class="btn btn-primary" href="/courses">
  មើលវគ្គ
  <span class="visually-hidden">សិក្សា CSS</span>
</a>
~~~
stretched-link ពង្រីក clickable area តាម containing block; ត្រូវប្រើដោយប្រុងប្រយ័ត្ន ដើម្បីកុំឱ្យគ្រប់គ្រង links/actions ផ្សេងក្នុង card ខុស។ ratio helper ជួយរក្សា aspect ratio របស់ embed/media។

## Utility generation និង Sass Utility API
Bootstrap Sass utility API ផ្អែកលើ Sass maps និង configuration ដែលបង្កើត classes ដូច spacing, display, colors។ នៅ project ដែលប្រើ Sass អាចបន្ថែម utility custom ដោយកែ map និង compile; កុំ edit bootstrap.min.css ផ្ទាល់ ព្រោះការប្តូរនឹងបាត់ពេល update។

ទម្រង់ជាគំនិត (syntax ពិតតាម Bootstrap Sass version):
~~~scss
$utilities: map-merge(
  $utilities,
  (
    "cursor": (
      property: cursor,
      class: cursor,
      values: pointer default
    )
  )
);
~~~
Utility API មិនដូចសរសេរ CSS class ដោយដៃទេ; វាបង្កើត responsive/print variants តាម configuration។ សម្រាប់ project តូច class custom ក្នុង file ផ្ទាល់ខ្លួនអាចសាមញ្ញជាង។

## Utilities vs components
ប្រើ utility សម្រាប់ style តូច ឬ layout tweak; ប្រើ component class/custom component សម្រាប់ repeated concept ដែលមាន style/state ច្រើន។ កុំបង្កើត div class list វែង 10–15 tokens រាល់កន្លែង បើវាបង្ក pattern ដែលគួរមានឈ្មោះ។

## អនុវត្ត
ប្រើ visually-hidden ដាក់ label ជំនួយ; សាក focus-ring និង ratio helper; បង្កើត custom class .u-text-balance ក្នុង stylesheet ផ្ទាល់ខ្លួន។ បើមាន Sass setup សាកបន្ថែម utility មួយតាម Utility API ហើយ compile។

## សំណួរ
1. visually-hidden ខុសពី display:none ដូចម្តេច?
2. ហេតុអ្វីមិនកែ bootstrap.min.css ផ្ទាល់?
3. តើពេលណា custom component class សមជាង utility chain?

**ចម្លើយ**៖ visually-hidden នៅសម្រាប់ assistive tech ខណៈ display:none ជាទូទៅដកពី layout/accessibility tree; update នឹងសរសេរជាន់; ពេល pattern style/state កើតឡើងជាញឹកញាប់ និងគួរមានឈ្មោះច្បាស់។