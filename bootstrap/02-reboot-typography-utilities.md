# Chapter 02៖ Reboot, Typography និង Utility Classes

## គោលបំណង
យល់ default styles របស់ Bootstrap, typography helpers និងរបៀបប្រើ utility classes ដោយរក្សា HTML ឱ្យមានអត្ថន័យ។

## Reboot
Bootstrap Reboot កំណត់ browser defaults ឱ្យស្របគ្នា និងបង្កើត baseline សម្រាប់ elements ដូចជា box-sizing, body, headings, links, forms។ វាមិនមែន reset ដែលលុប style ទាំងអស់ទេ។ ពេលភ្ជាប់ Bootstrap អត្ថបទ HTML ទទួល base styling ស្រាប់។

## Typography
~~~html
<h1 class="display-4">ចំណងជើងធំ</h1>
<p class="lead">កថាខណ្ឌបើកដែលលេចធ្លោជាងអត្ថបទធម្មតា។</p>
<p class="text-start">តម្រឹមទៅចំណុចចាប់ផ្តើមអត្ថបទ។</p>
<p class="fw-bold">អត្ថបទដិត</p>
<p class="text-body-secondary">អត្ថបទបន្ទាប់បន្សំ</p>
~~~
ប្រើ heading tags តាម hierarchy ពិត; display class ផ្លាស់ទំហំប៉ុណ្ណោះ មិនបង្កើត semantic heading ទេ។ Bootstrap v5.3 មាន theme colors និង text utilities ផ្សេងពី v4; ពិនិត្យ docs version ត្រឹមត្រូវ។

## Utility classes
Utility class គឺ class តូចមួយដែលប្តូរ property មួយ ឬក្រុមតូចៗ៖ color, spacing, display, flex, text alignment, border។ ឧទាហរណ៍ **text-center**, **bg-light**, **rounded**, **shadow-sm**។ Responsive variant អាចបន្ថែម breakpoint ដូច **text-md-start**។

ប្រើ utility សម្រាប់ tweak តូចៗ ឬ layout; បើ component មានរចនាប័ទ្មជាប់គ្នាច្រើន និងត្រូវ reuse សូមបង្កើត class semantic ផ្ទាល់ខ្លួន (ឧ. .profile-card) ជំនួស class chain វែងៗគ្រប់ទីកន្លែង។

## Khmer font
Bootstrap មិនធានាថាគ្រប់ប្រព័ន្ធមាន font Khmer ដូចគ្នាទេ។ បង្កើត custom CSS override:
~~~css
body {
  font-family: "Noto Sans Khmer", "Khmer OS", sans-serif;
  line-height: 1.7;
}
~~~
សាកល្បង font rendering, wrapping និង line-height លើទូរស័ព្ទ/desktop។

## អនុវត្ត
បង្កើត section មាន display heading, lead paragraph, secondary text និង button។ ពិនិត្យក្នុង DevTools ថា Reboot កំណត់ body/heading ដូចម្តេច។ បន្ថែម CSS ផ្ទាល់ខ្លួនតែសម្រាប់ Khmer font និង component ដែលត្រូវការ។

## សំណួរ
1. Reboot ធ្វើអ្វី?
2. display-4 ប្តូរ semantic level របស់ heading ដែរឬទេ?
3. តើពេលណាគួរបង្កើត custom class ជំនួស utility ច្រើន?

**ចម្លើយ**៖ កំណត់ baseline browser styles; មិនប្តូរ semantic level; ពេល style ជាច្រើនបង្កើត pattern reusable ឬ class chain ពិបាកអាន។