# មេរៀន ២២៖ Modern CSS UI/UX Design

## គោលបំណង
បង្កើត design system សាមញ្ញ និងប្រើវាសម្រាប់ button, card, navigation, hero, form, modal, dropdown និង dashboard។

## ១. Design tokens
~~~css
:root {
  color-scheme: light;
  --color-brand: #0b5f73;
  --color-text: #17212b;
  --color-surface: #ffffff;
  --color-muted: #eef3f5;
  --space-1: 0.25rem;
  --space-2: 0.5rem;
  --space-3: 1rem;
  --space-4: 1.5rem;
  --radius: 0.75rem;
  --shadow: 0 8px 24px rgb(15 40 55 / 12%);
}
~~~
Design system ជាសំណុំច្បាប់/tokens/components ដែលជួយឱ្យ UI មានភាពស្របគ្នា។ កុំប្រើពណ៌/spacing random រាល់ element; កំណត់ scale តូចដែលមានគោលបំណង។

## ២. Typography និង spacing system
ជ្រើស font stack ដែលគាំទ្រខ្មែរ, កំណត់ type scale និង line-height អានងាយ។ កំណត់ spacing scale ដូច 4, 8, 16, 24, 32 px (ឬ rem equivalents) ហើយប្រើ tokens។ ប្រើ white space ដើម្បីបែងចែក content ជាក្រុម មិនមែនបន្ថែមគ្រប់ទីកន្លែងដោយមិនគិត hierarchy។

## ៣. Components
~~~css
.button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-height: 2.75rem;
  padding: 0.65rem 1rem;
  border: 0;
  border-radius: var(--radius);
  background: var(--color-brand);
  color: white;
  font: inherit;
  cursor: pointer;
}
.button:focus-visible { outline: 3px solid orange; outline-offset: 3px; }
.card { padding: var(--space-4); background: var(--color-surface); border-radius: var(--radius); box-shadow: var(--shadow); }
~~~
Buttons ត្រូវជា <button> សម្រាប់ action និង <a> សម្រាប់ navigation។ Card ត្រូវមាន heading និង content semantic។ Navigation bar ត្រូវដំណើរការដោយ keyboard។ Hero ត្រូវមាន title/action ដែលមាន contrast; Product grid អាចប្រើ Grid auto-fit/minmax។

## ៤. Forms, modal និង dropdown
CSS អាចបង្ហាញ focus/error state ប៉ុន្តែ label, validation, open/close, focus trap/return និង keyboard behavior ត្រូវធ្វើដោយ HTML/JavaScript ត្រឹមត្រូវ។ កុំបង្កើត modal ដោយ CSS តែប៉ុណ្ណោះ ហើយគិតថា accessible រួច។ Dropdown ត្រូវអាចប្រើ keyboard និងអាន state បាន។

## ៥. Dark mode
~~~css
:root { color-scheme: light dark; }
:root {
  --surface: #fff;
  --text: #17212b;
}
@media (prefers-color-scheme: dark) {
  :root {
    --surface: #111827;
    --text: #f9fafb;
  }
}
body { background: var(--surface); color: var(--text); }
~~~
កំណត់ tokens ជំនួសការកែពណ៌រាល់ selector។ ពិនិត្យ contrast, border, shadow, input, image និង focus នៅ theme ទាំងពីរ។ បើមាន toggle ត្រូវបង្កើត state ដោយ JavaScript និងរក្សា preference ដោយច្បាស់។

## ៦. Responsive dashboard និង Khmer-inspired UI
Dashboard ប្រើ Grid សម្រាប់ sidebar/content និង Flexbox សម្រាប់ toolbar; នៅ mobile អាចប្តូរជួរឈរ និងធ្វើ sidebar ជា accessible navigation។ Khmer-inspired design អាចយក palette ពីធម្មជាតិ/វប្បធម៌ជាគំនិត ប៉ុន្តែត្រូវផ្តល់ priority ដល់ readability, Khmer typeface support, spacing សមស្របនឹងអក្សរ និង mobile usability។ កុំប្រើលំនាំតុបតែងដែលធ្វើឱ្យអត្ថបទរញ៉េរញ៉ៃ។

## អនុវត្តចុងវគ្គ
រចនា dashboard មាន header, navigation, cards, form និង dark theme។ បង្កើត token file, responsive grid, focus states, reduced-motion support និង test Khmer content។ កត់ត្រា design decisions និង browser/device ដែលបានសាក។

## សំណួរពិនិត្យ
1. Design token ជួយអ្វី?
2. Action button និង navigation link គួរប្រើ element អ្វី?
3. តើ CSS តែមួយគ្រប់គ្រាន់សម្រាប់ modal accessible ដែរឬទេ?
4. តើត្រូវពិនិត្យអ្វីខ្លះពេលបន្ថែម dark mode?

**ចម្លើយ**៖ ធ្វើឱ្យ style ស្របគ្នា និងងាយកែ; button សម្រាប់ action, a សម្រាប់ navigation; មិនគ្រប់គ្រាន់—ត្រូវមាន semantic/keyboard/focus behavior; ពិនិត្យ contrast, states, form controls, focus, images និង shadow។