# មេរៀន ១៦៖ CSS Transitions

## គោលបំណង
ធ្វើឱ្យការផ្លាស់ប្តូរ style រវាង state រលូន និងទាន់ពេល ដោយរក្សា accessibility។

## Properties
~~~css
.button {
  background-color: #155e75;
  transform: translateY(0);
  transition: background-color 180ms ease, transform 180ms ease;
}
.button:hover {
  background-color: #0e7490;
  transform: translateY(-2px);
}
~~~
Transition ត្រូវមាន property ដែលអាច animate បាន និង state ចាប់ផ្តើម/បញ្ចប់។ duration ជាពេល; timing-function ដូច ease, linear, ease-in-out ឬ cubic-bezier; delay គឺពេលរង់ចាំ។ **transition: all** អាចបង្កឱ្យ property មិនចង់ animate និងថ្លៃដំណើរការ; រាយ properties ដែលចង់ប្តូរ។

## Shorthand និង focus state
~~~css
.card {
  transition: box-shadow 200ms ease, transform 200ms ease;
}
.card:hover,
.card:focus-within {
  transform: translateY(-3px);
  box-shadow: 0 10px 30px rgb(0 0 0 / 14%);
}
~~~
កុំធ្វើ effect ដែលអាច hover តែប៉ុណ្ណោះ; គិត focus-within សម្រាប់ keyboard។ Transition ជាផលប៉ះពាល់តុបតែង មិនត្រូវលាក់មាតិកាចាំបាច់។

## Reduced motion
~~~css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    scroll-behavior: auto !important;
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
~~~
នេះជាគំរូទូទៅ; សម្រាប់ app ពិត អាចកាត់បន្ថយ motion តាម component ជាក់លាក់ជំនួសការលុប transition ទាំងអស់។ គោរព preference របស់ប្រព័ន្ធអ្នកប្រើ។

## អនុវត្ត
ធ្វើ button មាន hover/focus state transition ពណ៌ និង transform 150ms។ បើក OS reduced-motion ហើយផ្ទៀងផ្ទាត់ថា motion ត្រូវកាត់បន្ថយ។

## សំណួរ
1. Transition ត្រូវការអ្វីពីរដើម្បីកើតឡើង?
2. ហេតុអ្វីជៀសវាង transition:all?
3. prefers-reduced-motion ប្រាប់អ្វី?

**ចម្លើយ**៖ state មុន/ក្រោយ និង property ដែលអាច transition; all អាច animate អ្វីមិនចង់បាន និងធ្វើឱ្យ debugging/performance ពិបាក; វាបង្ហាញថាអ្នកប្រើចង់បាន motion តិច។