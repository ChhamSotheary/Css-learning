# មេរៀន ៥៖ Text និង Typography

## គោលបំណង
រៀបចំអក្សរឱ្យច្បាស់ អានងាយ និងបង្ហាញខ្មែរបានល្អលើឧបករណ៍ផ្សេងៗ។

## Properties សំខាន់
~~~css
body {
  color: #202124;
  font-family: "Noto Sans Khmer", "Khmer OS", sans-serif;
  font-size: 1rem;
  line-height: 1.7;
}
h1 {
  font-size: 2rem;
  font-weight: 700;
  font-style: normal;
  text-align: center;
}
a { text-decoration: underline; }
.label { text-transform: uppercase; }
p { text-indent: 1em; }
~~~
- **font-family** គួរមាន fallback font ចុងក្រោយដូច sans-serif។
- **font-size** កំណត់ទំហំ; ប្រើ rem សម្រាប់ scale ដែលស្របគ្នា។
- **font-weight** ជាទូទៅ 400 ធម្មតា, 700 bold (អាស្រ័យ font មាន weight)។
- **line-height** គ្មាន unit ជាទូទៅល្អសម្រាប់កែតាមទំហំអក្សរ។
- **text-align** កំណត់ alignment; **text-decoration** កំណត់ underline/line; **text-transform** បម្លែងការបង្ហាញអក្សរឡាតាំង។
- **letter-spacing** និង **word-spacing** កែចន្លោះ; ប្រើប្រុងប្រយ័ត្នសម្រាប់អក្សរខ្មែរ ព្រោះសញ្ញាវណ្ណយុត្តិ និង combining marks អាចមើលមិនស្អាត។
- **text-indent** កំណត់ការចូលបន្ទាត់ដំបូង។

## Khmer fonts និង web fonts
ប្រព័ន្ធអ្នកប្រើអាចមិនមាន font ខ្មែរដូចគ្នា។ ប្រើ font stack ដែលមាន fallback និងសាកល្បងលើទូរស័ព្ទ/desktop។ អាច self-host font ដែលមានអាជ្ញាប័ណ្ណត្រឹមត្រូវ; កុំភ្ជាប់ third-party font ដោយមិនគិត privacy/performance។ បើប្រើ Google Fonts សូមពិនិត្យថាមាន Khmer subset និងអាជ្ញាប័ណ្ណសមស្រប ហើយមាន fallback។

~~~css
@font-face {
  font-family: "CourseKhmer";
  src: url("../fonts/course-khmer.woff2") format("woff2");
  font-display: swap;
}
body { font-family: "CourseKhmer", sans-serif; }
~~~
ឈ្មោះ file និង font-family ត្រូវផ្គូផ្គងជាមួយ file ពិត។

## អនុវត្ត
បង្កើតអត្ថបទខ្មែរមួយកថាខណ្ឌ។ សាក font stack, font-size 1rem, line-height 1.7, កែ width អត្ថបទឱ្យប្រហែល 60–75 តួអក្សរឡាតាំងក្នុងមួយបន្ទាត់ (ប្រើ max-width ជា ch)។ សាកនៅទំហំអេក្រង់តូច។

## លំហាត់
1. ហេតុអ្វីគួរដាក់ fallback font?
2. តើ line-height: 1.6 មានន័យយ៉ាងដូចម្តេច?
3. តើ text-transform បម្លែងអក្សរខ្មែរបានទេ?

**ចម្លើយ**៖ Fallback បើ font ដើមមិនមាន/load មិនបាន; line-height គុណនឹង font-size; text-transform មានប្រសិទ្ធភាពជាពិសេសលើអក្សរដែលមាន uppercase/lowercase ដូចឡាតាំង មិនបម្លែងអក្សរខ្មែរទេ។