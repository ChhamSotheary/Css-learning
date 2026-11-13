# មេរៀន ១៨៖ CSS Animations

## គោលបំណង
កំណត់ animation ជាបន្តបន្ទាប់ដោយ @keyframes, properties និង accessibility motion preference។

## Keyframes និងការប្រើ
~~~css
@keyframes fade-up {
  from { opacity: 0; transform: translateY(0.75rem); }
  to { opacity: 1; transform: translateY(0); }
}
.notice {
  animation: fade-up 400ms ease-out both;
}
~~~
@keyframes ដាក់ចំណុចចាប់ផ្តើម/បញ្ចប់ ឬ percentage (0%,50%,100%)។ animation-name ភ្ជាប់ទៅ keyframes; duration កំណត់ពេល; delay រង់ចាំ; iteration-count កំណត់ចំនួន ឬ infinite; direction កំណត់ alternate/reverse; fill-mode គ្រប់គ្រង style មុន/ក្រោយ; timing-function កំណត់ល្បឿន។

## Shorthand និង properties
~~~css
.loader {
  animation: spin 900ms linear infinite;
}
@keyframes spin {
  to { transform: rotate(1turn); }
}
~~~
Shorthand លំដាប់ធម្មតា៖ name, duration, timing, delay, iteration, direction, fill, play state។ ដាក់ឈ្មោះច្បាស់ និងកំណត់ duration សមរម្យ។ Infinite animation ត្រូវមានមូលហេតុដូច loading; កុំ animate ដើម្បីតុបតែងឥតឈប់។

## Reduced motion និង state
~~~css
@media (prefers-reduced-motion: reduce) {
  .notice { animation: none; }
}
~~~
សម្រាប់ loading indicator ផ្តល់សញ្ញាដែលមិនពឹងលើចលនាតែមួយ ហើយឱ្យ screen reader អានស្ថានភាពតាម HTML/ARIA ត្រឹមត្រូវ។ CSS animation មិនបញ្ជាក់ថា data loading ពិតទេ។

## អនុវត្ត
បង្កើត loader តូចដែល spin និង button success មាន animation ម្តង។ បន្ថែម reduced-motion rule ហើយពិនិត្យករណី infinite/delay/fill-mode។

## សំណួរ
1. @keyframes កំណត់អ្វី?
2. animation-iteration-count:infinite សមស្របពេលណា?
3. តើអ្នកប្រើ reduced-motion preference ដូចម្តេច?

**ចម្លើយ**៖ ស៊េរី style តាមពេល; សម្រាប់ចលនាបន្តដែលមានអត្ថន័យដូច loading និងមាន alternative; បិទ/កាត់បន្ថយចលនាតាម preference។