# មេរៀន ២០៖ Cascade, Specificity និង Modern CSS

## គោលបំណង
ដោះស្រាយ style conflict ដោយយល់ពី cascade, inheritance, specificity និងសរសេរ CSS សម័យថ្មីដោយមាន fallback។

## Cascade ជ្រើស rule យ៉ាងដូចម្តេច?
ពេលច្រើន declaration កំណត់ property ដូចគ្នា browser ពិចារណា source/origin និង importance, cascade layer, specificity, scoping proximity ក្នុងករណីពាក់ព័ន្ធ, រួច source order។ សម្រាប់ style author ធម្មតាដែលមិនស្មុគស្មាញ៖ rule ក្នុង layer ក្រោយមាន priority ខ្ពស់ជាង layer មុន; ក្នុង layer ដូចគ្នា specificity និង order សម្រេច។ !important ប្តូរលំដាប់អាទិភាព ដូច្នេះកុំប្រើជាដំណោះស្រាយទូទៅ។

Specificity សង្ខេប៖ ID មានទម្ងន់ខ្ពស់ជាង class/attribute/pseudo-class; class/attribute/pseudo-class ខ្ពស់ជាង type/pseudo-element។ Universal selector និង :where() មាន specificity សូន្យ។ :is(), :not(), :has() យក specificity ពី selector list ខាងក្នុងដែលខ្ពស់បំផុត។ Source order សម្រេចតែពេលចំណាត់ថ្នាក់មុនស្មើ។

~~~css
@layer reset, base, components, utilities;
@layer base {
  h1 { color: #222; }
}
@layer components {
  .title { color: navy; }
}
~~~
Declare layer order មុន ដើម្បីឱ្យអាទិភាពច្បាស់។ Normal declarations ក្នុង layer ក្រោយឈ្នះ layer មុន; unlayered normal styles ជាទូទៅលើ layers។ !important មានលំដាប់ layer បញ្ច្រាស។ សម្រាប់ project តូច សរសេរច្បាប់ layer ឱ្យសាមញ្ញ ហើយសាកក្នុង DevTools។

## Inheritance និង !important
Properties ដូច color/font ជាច្រើន inherit; margin/border ជាទូទៅមិន inherit។ inherit បង្ខំទទួលពី parent; initial reset ទៅ initial value; unset ជា inherit ឬ initial តាម property។ !important គួរតែប្រើតែពេលមានហេតុផលច្បាស់ (ឧ. utility override policy), ព្រោះធ្វើឱ្យ override ក្រោយពិបាក។

## CSS nesting
~~~css
.card {
  padding: 1rem;

  & h2 { margin-block-start: 0; }
  &:hover { box-shadow: 0 8px 24px #0002; }
}
~~~
Nesting ជួយដាក់ style ជិតគ្នា ប៉ុន្តែកុំ nest ជ្រៅ; code ដែលសរសេរខ្លីអាចបង្ក selector specificity ខ្ពស់ និងពិបាកអាន។ សាកល្បង browser support របស់ audience ឬប្រើ build tooling ដែលបានកំណត់ក្នុង project។

## Logical properties
~~~css
.card {
  margin-inline: auto;
  padding-block: 1rem;
  border-inline-start: 4px solid teal;
}
~~~
inline/block ជំនួស left/right/top/bottom ដើម្បីសមនឹង writing direction។ វាជួយ multilingual layout រួមទាំង RTL។ ប្រើ logical properties ក្នុង component ថ្មី និងសាកល្បងទិសអក្សរបើគម្រោងគាំទ្រ។

## Container queries
~~~css
.card-list { container-type: inline-size; }
@container (min-width: 36rem) {
  .card { display: grid; grid-template-columns: 8rem 1fr; }
}
~~~
Media query ឆ្លើយតបតាម viewport; container query ឆ្លើយតបតាមទំហំ container។ ត្រូវបង្កើត query container (ឧ. container-type:inline-size)។ វាមានប្រយោជន៍សម្រាប់ reusable component ក្នុង sidebar និង main area ដែលទទឹងខុសគ្នា។ ត្រូវពិនិត្យ browser target និងមាន base style ដែលដំណើរការបើ query មិន match។

## @supports feature query
~~~css
@supports (display: grid) {
  .layout { display: grid; }
}
~~~
@supports ពិនិត្យថា browser គាំទ្រការប្រកាស CSS មួយឬអត់ ហើយអាចបង្កើត fallback។ វាមិនជំនួសការសាក browser ពិតទេ។

## អនុវត្ត
បើក DevTools ហើយសិក្សា rule ដែលឈ្នះលើ button។ បង្កើត layer reset/base/components/utilities, ប្រើ :where() សម្រាប់ selector មូលដ្ឋាន និង container query សម្រាប់ card។ កត់ត្រា fallback ដែលគម្រោងត្រូវការ។

## លំហាត់
1. បើ specificity ស្មើគ្នា តើអ្វីអាចសម្រេចអ្នកឈ្នះ?
2. :where() ជួយអ្វី?
3. Media query និង container query ខុសគ្នាដូចម្តេច?
4. ហេតុអ្វី !important ច្រើនធ្វើឱ្យថែទាំពិបាក?

**ចម្លើយ**៖ Source order អាចសម្រេច; :where() មាន specificity សូន្យ ងាយ override; media query មើល viewport ខណៈ container query មើលទំហំ container; important បង្កើត priority ដែល rule ធម្មតាពិបាក override។