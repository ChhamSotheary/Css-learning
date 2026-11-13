# មេរៀន ១៩៖ CSS Variables និង Functions

## គោលបំណង
បង្កើត design tokens ដែលប្រើឡើងវិញបាន និងគណនាតម្លៃ responsive ដោយ calc(), min(), max(), clamp()។

## Custom properties និង scope
~~~css
:root {
  --color-brand: #075985;
  --space-3: 1rem;
  --radius-card: 0.75rem;
}
.card {
  color: var(--color-brand);
  padding: var(--space-3);
  border-radius: var(--radius-card);
}
~~~
Custom property ឈ្មោះចាប់ផ្តើម -- ហើយប្រើ var()។ វា cascade និង inherit ដូច properties ផ្សេងៗ។ :root ជាធម្មតាមាន scope ទូទាំង document; អ្នកអាចកំណត់លើ component ដើម្បី override តាមតំបន់។ អាចមាន fallback៖ **var(--color, black)**។

~~~css
[data-theme="dark"] {
  --surface: #111827;
  --text: #f9fafb;
}
~~~
កំណត់ tokens សម្រាប់ theme ឱ្យ component ប្រើ **var(--surface)** ជំនួសពណ៌ hardcode។

## Functions សម្រាប់ទំហំ
~~~css
.panel { width: calc(100% - 2rem); }
.container { width: min(100% - 2rem, 72rem); }
.media { width: max(20rem, 50%); }
h1 { font-size: clamp(1.75rem, 4vw + 1rem, 3.5rem); }
~~~
- calc() គណនា expression; ដក/បូកត្រូវមាន whitespace ជុំវិញ operator។
- min() យកតម្លៃតូច; max() យកតម្លៃធំ។
- clamp(min, preferred, max) បង្ខំតម្លៃឱ្យនៅចន្លោះកំណត់។

## attr()
~~~css
a::after { content: " (" attr(href) ")"; }
~~~
attr() ត្រូវបានប្រើជាទូទៅក្នុង generated content ដើម្បីអាន string attribute។ ការប្រើ attr() ជា type ផ្សេងៗ (ឧ. length) ជា feature ដែលត្រូវពិនិត្យ support តាម browser target; កុំសន្មតថាអនុវត្តបានគ្រប់ទីកន្លែង។

## អនុវត្ត
បង្កើត tokens សម្រាប់ color, spacing, radius; បន្ថែម dark theme តាម data-theme។ កែ container width និងចំណងជើងដោយ min/max/clamp។ ប្ដូរ token មួយ ហើយសង្កេតគ្រប់ component។

## លំហាត់
1. តើ custom properties inherit ដែរឬទេ?
2. var() fallback មានតួនាទីអ្វី?
3. clamp(1rem, 3vw, 2rem) កំណត់អ្វី?

**ចម្លើយ**៖ inherit តាម cascade; fallback ប្រើពេល variable មិនមាន/មិន valid; preferred 3vw ត្រូវបានកាត់កុំឱ្យក្រោម 1rem ឬលើស 2rem។