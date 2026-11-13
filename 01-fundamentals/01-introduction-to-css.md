# មេរៀន ១៖ សេចក្តីផ្តើមអំពី CSS

## គោលបំណង
ក្រោយមេរៀននេះ អ្នកអាចពន្យល់ CSS, ប្រៀបធៀប HTML និង CSS, សរសេរ CSS rule និងភ្ជាប់រចនាប័ទ្មទៅ HTML។

## CSS ជាអ្វី?
CSS (Cascading Style Sheets) ជាភាសាសម្រាប់កំណត់របៀបបង្ហាញ HTML៖ ពណ៌, ទំហំ, ចន្លោះ, ទីតាំង, layout និង animation។ HTML កំណត់អត្ថន័យ/រចនាសម្ព័ន្ធ; CSS កំណត់រូបរាង។ ឧទាហរណ៍ HTML ប្រាប់ថា «នេះជាចំណងជើង» ខណៈ CSS កំណត់ពណ៌ និងទំហំចំណងជើង។

Browser អាន HTML បង្កើត DOM tree រួចអាន CSS និងគណនារចនាប័ទ្មដែលអនុវត្តទៅ element នីមួយៗ។ CSS អាចប្រកួតប្រជែងគ្នា; cascade ជ្រើស rule ដែលមានអាទិភាពសមស្រប (រៀនលម្អិតនៅមេរៀន ២០)។

## Syntax: rule, selector និង declaration
~~~css
h1 {
  color: navy;
  font-size: 2rem;
}
~~~
- **Selector**: h1 — ជ្រើស element គោលដៅ។
- **Declaration block**: ខ្លឹមសារក្នុង { }។
- **Property**: color ឬ font-size។
- **Value**: navy ឬ 2rem។
- បញ្ចប់ declaration ដោយ semicolon **;**។ ដាក់មួយ declaration ក្នុងមួយបន្ទាត់ ដើម្បីងាយអាន។

CSS comment មិនបង្ហាញលើទំព័រ៖ **/* comment */**។ ឯកសារ CSS ប្រើ extension **.css**។

## ឧទាហរណ៍ជាមួយ HTML
~~~html
<h1>ស្វាគមន៍</h1>
<p>នេះជាទំព័រដំបូងរបស់ខ្ញុំ។</p>
~~~
~~~css
h1 {
  color: #14532d;
}
p {
  line-height: 1.6;
}
~~~

## កំហុសដែលជួបញឹកញាប់
- ភ្លេចសញ្ញា **{ }** ឬ semicolon។
- សរសេរ property ខុសអក្ខរាវិរុទ្ធ (ឧ. **colr**)។
- សរសេរ HTML ក្នុងឯកសារ .css ឬ CSS ក្នុងទីតាំងខុស។
- គិតថា CSS ជំនួស HTML; វាបំពេញគ្នា មិនជំនួសគ្នាទេ។

## អនុវត្ត
បង្កើតឯកសារ HTML មាន h1, paragraph និង link។ សរសេរ CSS ដាក់ពណ៌ h1, កំណត់ទំហំអក្សរ និងបន្ថែម comment ពន្យល់គោលបំណង rule។

## លំហាត់
1. ពន្យល់ភាពខុសគ្នារវាង HTML និង CSS ជាពាក្យរបស់អ្នក។
2. ក្នុង rule ខាងលើ តើ selector, property និង value ជាអ្វី?
3. បន្ថែម rule សម្រាប់ paragraph ដែលកំណត់ margin-bottom។

## ចម្លើយខ្លី
1. HTML ជារចនាសម្ព័ន្ធ/អត្ថន័យ; CSS ជារូបរាង និង layout។
2. Selector = h1; properties = color, font-size; values = navy, 2rem។
3. ឧទាហរណ៍៖ p { margin-bottom: 1rem; }។