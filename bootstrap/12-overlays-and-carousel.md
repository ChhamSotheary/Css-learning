# Chapter 12៖ Modal, Toast, Tooltip, Popover និង Carousel

## Modal
Modal dialog សម្រាប់ការងារដែលត្រូវការការយកចិត្តទុកដាក់ ឬ input បន្ថែម។ Trigger អាចមាន data-bs-toggle="modal" និង data-bs-target="#exampleModal"។ Modal ត្រូវការ title/aria-labelledby, close button ដែលមាន accessible label និង focus behavior។ កុំបើក modal លើ modal ផ្សេងៗដោយគ្មាន design ច្បាស់។

## Toast
Toast បង្ហាញសារខ្លីៗមិនចាំបាច់រារាំងការងារ។ ប្រើ role/status ឬ aria-live តាម urgency; កុំ auto-dismiss សារដែលអ្នកប្រើត្រូវអាន/ធ្វើសកម្មភាព។ Toast behavior ត្រូវ initialize/show ដោយ Bootstrap JS ឬ data API។

## Tooltip និង Popover
Tooltip ផ្តល់ពាក្យពន្យល់ខ្លី; Popover មានចំណងជើង/content ច្រើនជាង។ ត្រូវការ Popper។ Tooltip មិនគួរផ្ទុកព័ត៌មានចាំបាច់តែមួយកន្លែងទេ ហើយត្រូវអាចបើកដោយ keyboard focus មិនមែន hover តែប៉ុណ្ណោះ។ Initialize tooltip តាម JS៖
~~~js
const tooltipTriggerList = document.querySelectorAll('[data-bs-toggle="tooltip"]');
[...tooltipTriggerList].forEach((el) => new bootstrap.Tooltip(el));
~~~
ពិនិត្យ Bootstrap version និង module setup; ប្រសិនបើ bundle និង modules ផ្សេង សូមប្រើ initialization ត្រឹមត្រូវ។ Dispose instance បើ element ត្រូវលុប/re-render ក្នុង app។

## Carousel
Carousel បង្ហាញ slide ម្តងមួយ និង controls/indicators។ ផ្តល់ button labels, pause control ប្រសិនបើ auto-rotate, និងកុំឱ្យ motion បង្កការរំខាន។ អ្នកប្រើត្រូវអាចឈប់/គ្រប់គ្រង autoplay; content នៃ slide ត្រូវមាន semantics និង alt រូបត្រឹមត្រូវ។

## ច្បាប់ accessibility សម្រាប់ overlays
- Modal: focus move ចូល, Escape/close, focus return និង dialog name ត្រូវបានសាកល្បង។
- Tooltip: មិនដាក់ links/forms ដែលស្មុគស្មាញ; ប្រើ popover/dialog pattern ប្រសិនបើ interactive។
- Toast: live-region announcement សមស្រប និងមិនបាត់លឿនពេក។
- Carousel: អ្នកប្រើអាច pause/forward/back និងយល់ថា slide កំពុងណា។

## អនុវត្ត
បង្កើត modal confirm action, toast success និង tooltip លើ help icon; សាក keyboard និង screen reader។ ប្រើ carousel តែពេលមាន content ជាច្រើនដែលមានប្រយោជន៍ និងបន្ថែម pause control ប្រសិនបើ autoplay។

## សំណួរ
1. តើ tooltip គួរផ្ទុកព័ត៌មានសំខាន់តែមួយកន្លែងទេ?
2. តើ modal ត្រូវធ្វើ focus return ទៅ trigger ដែរឬទេ?
3. ហេតុអ្វី autoplay carousel ត្រូវមាន pause?

**ចម្លើយ**៖ មិនគួរ; គួរតែរក្សា keyboard flow និង focus return; ដើម្បីឱ្យអ្នកប្រើគ្រប់គ្រងចលនា និងអានបាន។