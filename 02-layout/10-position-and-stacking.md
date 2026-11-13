# មេរៀន ១០៖ Position និង Stacking Context

## គោលបំណង
ដាក់ element ក្នុង flow, anchor absolute child ទៅ parent និងយល់ពី z-index/stacking context។

## Positioning modes
~~~css
.static { position: static; } /* default */
.relative { position: relative; top: 0.5rem; }
.badge { position: absolute; top: 0.5rem; right: 0.5rem; }
.toolbar { position: fixed; bottom: 1rem; right: 1rem; }
header { position: sticky; top: 0; }
~~~
- **static** នៅ normal flow; top/right/bottom/left មិនប្រើ។
- **relative** នៅកន្លែងដើមក្នុង flow តែអាចប្តូរមើលឃើញ; ជាញឹកញាប់ធ្វើ containing block សម្រាប់ absolute child។
- **absolute** ដកចេញពី normal flow ហើយដាក់ធៀប containing block ដែលជិតបំផុតដែល position មិន static។
- **fixed** ដាក់ធៀប viewport ជាទូទៅ និងនៅទីតាំងពេល scroll; ancestor transform/filter អាចបង្កើត containing block ផ្សេង។
- **sticky** ដំបូងនៅ flow បន្ទាប់មកជាប់ព្រំដែន scroll container; ត្រូវកំណត់ offset ឧ. top:0។

## z-index និង stacking
~~~css
.card { position: relative; }
.card__badge { position: absolute; z-index: 2; }
~~~
z-index គ្រប់គ្រងលំដាប់គំនូរក្នុង stacking context; វាមិនមែនជាលេខសកលទេ។ Element ខាងក្នុង context មួយមិនអាចឡើងលើ context ខាងក្រៅដោយបន្ថែមលេខធំជានិច្ចឡើយ។ opacity តិចជាង 1, transform, isolation និង properties ផ្សេងអាចបង្កើត stacking context។

## ការប្រើប្រាស់ប្រកបដោយប្រុងប្រយ័ត្ន
កុំប្រើ absolute សម្រាប់ layout ទាំងមូល; វាអាច overlap ពេលអត្ថបទប្ដូរ/viewport តូច។ ប្រើ Flexbox/Grid សម្រាប់ layout; position សម្រាប់ badge, tooltip, overlay និង sticky header ដែលមានគោលបំណងច្បាស់។ ពិនិត្យ focus និង content ក្រោម fixed header។

## អនុវត្ត
ធ្វើ card position:relative និង badge absolute ខាងស្តាំលើ។ ធ្វើ navigation sticky ដោយ top:0 និង background ស្រអាប់ល្អ។ សាក zoom និង scroll។

## លំហាត់
1. តើ absolute child anchor ទៅណា?
2. ហេតុអ្វី z-index:9999 មិនតែងតែឈ្នះ?
3. តើ fixed element អាចបាំង content ដែរឬទេ?

**ចម្លើយ**៖ containing block ជិតបំផុតដែល positioned; stacking context កំណត់ព្រំដែនលំដាប់; fixed UI អាច overlap ដូច្នេះត្រូវរៀប spacing/focus។