# មេរៀន ៩៖ Display, Visibility និង Overflow

## គោលបំណង
ស្គាល់ឥរិយាបថ block/inline, លាក់ element, និងប្រើ display flex/grid ជាមួយ overflow។

## Display មូលដ្ឋាន
~~~css
div { display: block; }
span { display: inline; }
.badge { display: inline-block; }
.hidden { display: none; }
~~~
- **block** ចាប់បន្ទាត់ថ្មី និងទទួលទំហំ block។
- **inline** នៅក្នុងបន្ទាត់; width/height មិនអនុវត្តដូច block។
- **inline-block** នៅក្នុងបន្ទាត់ ប៉ុន្តែអាចកំណត់ width/height និង padding បាន។
- **none** មិនបង្ហាញ និងមិនកាន់កន្លែង; វាក៏មិននៅក្នុង accessibility tree តាមរបៀបដែលបង្ហាញធម្មតាដែរ។

## លាក់ និង visibility
~~~css
.hidden { display: none; }
.invisible { visibility: hidden; }
.transparent { opacity: 0; }
~~~
visibility:hidden រក្សាកន្លែង តែអាចមិនមើលឃើញ; opacity:0 នៅរក្សា layout ហើយអាចនៅទទួល interaction/keyboard ដូច្នេះមិនមែនជាវិធីលាក់ interactive UI ល្អទេ។ ជ្រើសវិធីតាមបំណង និងគ្រប់គ្រង accessibility។

## Modern layout
~~~css
.row { display: flex; gap: 1rem; }
.gallery { display: grid; grid-template-columns: repeat(3, 1fr); }
~~~
Flexbox/Grid នឹងសិក្សាលម្អិតក្នុងមេរៀន 11–12។ កុំប្រើ display ដើម្បីបំបាត់ semantic HTML; ជ្រើស element ត្រឹមត្រូវជាមុន។

## Overflow
~~~css
.code-box {
  max-width: 100%;
  overflow: auto;
}
~~~
overflow:visible បង្ហាញ content លើស; hidden កាត់; clip កាត់ដោយគ្មាន scroll container; scroll បង្ហាញ scrollbars; auto បង្ហាញពេលចាំបាច់។ ប្រើ min-width:0 លើ flex/grid child នៅពេល content វែងធ្វើឱ្យ track លើស។

## អនុវត្ត
បង្កើត navigation links ជា inline-block ឬ flex; បង្កើត code panel មាន max-height និង overflow:auto។ សាក hide panel ដោយ display:none និង visibility:hidden ហើយកត់ថាកន្លែងនៅដដែលឬអត់។

## សំណួរ
1. display:none និង visibility:hidden ខុសគ្នាដូចម្តេច?
2. តើ inline-block អាចកំណត់ width/height ដែរឬទេ?
3. តើ overflow:auto ធ្វើអ្វី?

**ចម្លើយ**៖ none មិនរក្សាកន្លែង; visibility hidden រក្សាកន្លែង; inline-block អាចទទួល dimensions; auto scroll ពេល content លើស។