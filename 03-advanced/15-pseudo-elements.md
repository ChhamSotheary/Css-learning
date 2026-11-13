# មេរៀន ១៥៖ Pseudo-elements

## គោលបំណង
Style ផ្នែកមួយនៃ element ឬបង្កើត decoration បន្ថែមដោយ ::before/::after។

## ::before និង ::after
~~~css
.link::after {
  content: " ↗";
  color: teal;
}
.card::before {
  content: "";
  display: block;
  height: 0.25rem;
  background: teal;
}
~~~
Pseudo-element ត្រូវសរសេរ content property ដើម្បីបង្ហាញ; សម្រាប់គំនូសតុបតែង content:"" បាន។ វាមិនមែនជំនួស HTML សម្រាប់ព័ត៌មានសំខាន់ទេ ព្រោះ content generated អាចមិនអានដូចគ្នាដោយ assistive technology។

## Pseudo-elements ផ្សេងៗ
~~~css
p::first-letter { font-size: 2em; }
p::first-line { font-weight: 700; }
::selection { background: #fde68a; color: #111; }
input::placeholder { color: #666; opacity: 1; }
li::marker { color: teal; }
~~~
- **::first-letter/::first-line** style អក្សរ/បន្ទាត់ដំបូង តាមលក្ខខណ្ឌ CSS។
- **::selection** style text ដែលអ្នកប្រើ highlight។
- **::placeholder** style placeholder; កុំប្រើវាជំនួស label ព្រោះបាត់ពេលវាយ។
- **::marker** style bullet ឬលេខ list marker។

## Pseudo-class និង pseudo-element
Pseudo-class មួយសញ្ញាកូឡុង ដូច :hover; វាជ្រើស state។ Pseudo-element ពីរកូឡុង ដូច ::before; វាជ្រើសផ្នែករង/បង្កើត box។ Browser នៅគាំទ្រសរសេរ pseudo-element ចាស់ដោយកូឡុងតែមួយខ្លះៗ ប៉ុន្តែប្រើ :: សម្រាប់ភាពច្បាស់។

## អនុវត្ត
បង្កើត link external មានសញ្ញាតុបតែង, list marker ពណ៌ និង selection highlight។ សាក screen reader/keyboard ហើយធានាព័ត៌មានសំខាន់មានក្នុង HTML។

## លំហាត់
1. តើ ::before ត្រូវការអ្វីដើម្បីបង្ហាញ?
2. ហេតុអ្វី placeholder មិនជំនួស label?
3. តើ ::marker អាចកែអ្វី?

**ចម្លើយ**៖ content; placeholder បាត់ពេលបញ្ចូលតម្លៃ ហើយអាចមាន contrast អន់; marker គឺ bullet/លេខ list។