# មេរៀន ២១៖ Professional CSS Architecture

## គោលបំណង
រៀបចំ CSS ដែលអាចអាន, ពង្រីក, reuse, test accessibility និងកាត់បន្ថយ style conflict។

## BEM naming
BEM ជាវិធីដាក់ឈ្មោះ Block, Element, Modifier៖
~~~html
<article class="card card--featured">
  <h2 class="card__title">ចំណងជើង</h2>
</article>
~~~
~~~css
.card { padding: 1rem; }
.card__title { margin: 0; }
.card--featured { border-color: teal; }
~~~
Block ជា component ឯករាជ្យ; element ជាផ្នែករបស់ block; modifier ជា variant/state។ BEM ជាគោលការណ៍មួយ មិនមែនស្តង់ដារចាំបាច់។ កុំបង្កើតឈ្មោះវែងពេក; ជ្រើស convention មួយស្របគ្នា។

## រៀបចំ stylesheet
គំរូ file structure សម្រាប់ project តូច/មធ្យម៖
~~~text
css/
├── tokens.css
├── base.css
├── layout.css
├── components/
│   ├── button.css
│   └── card.css
└── main.css
~~~
- **Tokens**៖ color, spacing, type scales។
- **Base**៖ default/reset ស្រាល, typography, element base។
- **Layout**៖ container, page grid, spacing primitives។
- **Components**៖ button/card/form ជាដើម។
- **main.css**៖ import/link តាមលំដាប់ច្បាស់។

## Reset និង Normalize
Reset សម្រួល browser defaults; Normalize រក្សា default ដែលមានប្រយោជន៍ និងធ្វើឱ្យខុសគ្នារវាង browser តិច។ អាចប្រើ reset ស្រាលដោយខ្លួនឯង; កុំចម្លង reset ធំដោយមិនយល់។ រក្សា heading/semantic element មិនឱ្យបាត់ style/meaning សំខាន់។

## Reusable styles និងកុំ duplicate
ប្រើ custom properties សម្រាប់ tokens, component classes សម្រាប់ pattern និង utility classes តិចៗដែលមានគោលបំណង។ ជៀសវាង selector global ជ្រៅៗដូច .page .main .card h2; វាភ្ជាប់ style ទៅ DOM structure និងងាយបែកពេល markup ប្តូរ។ កុំបង្កើត abstraction មុនពេលមាន pattern ពិត។

## Performance និង browser compatibility
- កាត់ CSS ដែលមិនប្រើនៅ production តាម build tool ដែល project ប្រើ។
- រក្សា stylesheet អានងាយ; កុំ optimize ដោយបង្រួម code ដោយដៃ។
- ប្រើរូបភាព/animation មានទំហំសម; CSS selector ស្មុគស្មាញខ្លាំងអាចធ្វើឱ្យថែទាំលំបាក។
- សាក browser និង device ដែល audience ប្រើ; កំណត់ support policy មុនដាក់ feature ថ្មី។
- ប្រើ feature detection/fallback ពេលចាំបាច់; កុំសន្មត browser compatibility ដោយគ្មានការផ្ទៀងផ្ទាត់។

## Accessibility checklist
- មាន focus indicator សម្រាប់ keyboard។
- ពណ៌អត្ថបទ/ផ្ទៃមាន contrast អានបាន។
- មិនពឹងលើពណ៌តែមួយដើម្បីបង្ហាញ error/success។
- ចលនាគោរព prefers-reduced-motion។
- Zoom/reflow នៅទទឹងតូចមិនកាត់មាតិកា។
- Label, semantic HTML និង focus order គ្រប់គ្រងក្នុង HTML/JS មិនអាចជួសជុលដោយ CSS ប៉ុណ្ណោះ។

## អនុវត្ត
រៀបចំ mini site 3 pages ដោយ tokens, base, layout និង component files។ ប្រើ BEM ឬ naming convention មួយ, បង្កើត button/card reusable និងសរសេរ checklist ពិនិត្យ accessibility/browser។

## លំហាត់
1. តើ BEM មានន័យអ្វី?
2. ហេតុអ្វីមិនគួរប្រើ selector ជ្រៅ?
3. តើ CSS អាចជំនួស semantic HTML បានទេ?

**ចម្លើយ**៖ Block Element Modifier; selector ជ្រៅភ្ជាប់នឹង DOM និងពិបាក override; មិនបានទេ—CSS គ្រប់គ្រង presentation ប៉ុណ្ណោះ។