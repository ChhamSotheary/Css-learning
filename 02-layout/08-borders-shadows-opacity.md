# មេរៀន ៨៖ Borders, Shadows និង Opacity

## គោលបំណង
បង្កើតស៊ុម, មុំមូល, outline និង shadow ដោយរក្សាការអាន និង focus state ឱ្យច្បាស់។

## Border និង radius
~~~css
.card {
  border: 1px solid #d1d5db;
  border-radius: 0.75rem;
}
.pill {
  border: 2px dashed teal;
  border-radius: 999px;
}
~~~
Border shorthand រួម **width style color**; style អាចជា solid, dashed, dotted, double, none។ radius អាចកំណត់ជ្រុងនីមួយៗ ឬ 50% សម្រាប់រង្វង់ (ប្រអប់ការ៉េ)។

## Outline និង Shadow
~~~css
button:focus-visible {
  outline: 3px solid #0b72e7;
  outline-offset: 3px;
}
.card { box-shadow: 0 8px 24px rgb(0 0 0 / 12%); }
.title { text-shadow: 0 1px 2px rgb(0 0 0 / 20%); }
~~~
Outline មិនយកកន្លែងក្នុង box model; កុំដក outline focus ចេញ លុះត្រាតែមាន replacement ដែលមើលឃើញច្បាស់។ Box shadow ទម្រង់សាមញ្ញ៖ offset-x, offset-y, blur, spread, color។ ប្រើស្រាលៗ ដើម្បីកុំឱ្យ component មើលធ្ងន់។

## Opacity
~~~css
.disabled-look { opacity: 0.55; }
.overlay { background: rgb(0 0 0 / 50%); }
~~~
opacity កំណត់ភាពថ្លារបស់ element និងកូនទាំងអស់; វត្ថុក្រោមអាចមើលឃើញ។ បើចង់ឱ្យតែផ្ទៃថ្លា ប្រើ color ដែលមាន alpha ជំនួស opacity លើ parent។ កុំប្រើ opacity តែមួយដើម្បីបង្ហាញ disabled; ត្រូវកំណត់ interaction semantics ក្នុង HTML/JS ផងដែរ។

## អនុវត្ត
រចនា profile card: border ស្រាល, radius, shadow ស្តើង; បង្កើត button មាន :focus-visible outline ខុសពី hover។ ប្រៀបធៀប background ជាមួយ rgba/alpha និង opacity។

## ពិនិត្យខ្លួនឯង
1. Outline ខុសពី border ត្រង់ណា?
2. ហេតុអ្វីមិនដាក់ opacity លើ card ពេលចង់ឱ្យផ្ទៃតែប៉ុណ្ណោះថ្លា?
3. តើ keyboard focus ត្រូវបង្ហាញទេ?

**ចម្លើយ**៖ Outline មិនប៉ះពាល់ box dimensions; opacity ធ្វើឱ្យកូនទាំងអស់ស្រអាប់; focus ត្រូវមើលឃើញសម្រាប់អ្នកប្រើ keyboard។