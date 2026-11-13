# មេរៀន ១៤៖ Pseudo-classes

## គោលបំណង
ជ្រើស element តាម state, ទីតាំងក្នុងបងប្អូន និង pattern ដោយមិនបន្ថែម class សម្រាប់គ្រប់ករណី។

## Interaction states
~~~css
a:hover { color: #075985; }
button:active { transform: translateY(1px); }
input:focus-visible { outline: 3px solid royalblue; }
a:visited { color: purple; }
input:checked + label { font-weight: 700; }
button:disabled { opacity: 0.55; cursor: not-allowed; }
~~~
:hover សម្រាប់ pointer; active ពេលចុច; focus ពេល keyboard/pointer focus; focus-visible ជួយបង្ហាញ focus ពេលសមស្របជាពិសេស keyboard។ កុំដក focus outline ចេញដោយគ្មាន replacement។ :visited មាន privacy restriction ដូច្នេះអនុញ្ញាត style តិច។

## Structural selectors
~~~css
li:first-child { font-weight: bold; }
li:last-child { border: 0; }
tr:nth-child(even) { background: #f5f5f5; }
.card:not(.featured) { border: 1px solid #ddd; }
~~~
nth-child គិតទីតាំងតាម siblings ទាំងអស់; nth-of-type គិតតាម type។ អាចប្រើ even/odd ឬ expression ដូច 3n។

## :is(), :where(), :has()
~~~css
:is(header, footer) a { color: inherit; }
:where(article, section) p { line-height: 1.6; }
.card:has(img) { padding-top: 0; }
~~~
:is() សង្ខេប selector list និង specificity តាម selector ក្នុងបញ្ជីដែលខ្ពស់បំផុត; :where() មាន specificity សូន្យ ងាយ override; :has() ជ្រើស parent/element ដោយផ្អែកលើកូនឬបងប្អូនដែល match។ ត្រូវពិនិត្យ browser support សម្រាប់ target របស់គម្រោង; ប្រើ @supports ឬ fallback ប្រសិនបើចាំបាច់។

## អនុវត្ត
បង្កើត form មាន input required, disabled button, checkbox និង list។ Style focus-visible, checked label, first/last item និង nth-child(even)។

## សំណួរ
1. :focus និង :focus-visible ខុសគ្នាដូចម្តេច?
2. :where() មានអត្ថប្រយោជន៍ specificity អ្វី?
3. :has() អាចជ្រើស parent តាម child បានដែរឬទេ?

**ចម្លើយ**៖ focus-visible ផ្តោតលើពេល browser ចាត់ទុក focus indicator គួរបង្ហាញ; :where() specificity សូន្យ; :has() អាចសាកល្បង descendant/relative selector របស់ element។