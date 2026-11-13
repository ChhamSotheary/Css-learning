# Chapter 15៖ Theme, CSS Variables និង Dark Mode

## Bootstrap color modes
Bootstrap 5.3 គាំទ្រ color modes និង CSS variables សម្រាប់កំណត់ពណ៌/appearance តាម theme។ Bootstrap components ខ្លះប្រើ CSS variables ដើម្បីអនុញ្ញាត override ជិត component។ កុំសន្មតថា class ទាំងអស់ប្តូរពណ៌ដោយស្វ័យប្រវត្តិ—ត្រូវសាក components ដែលប្រើ។

## ប្រើ data-bs-theme
~~~html
<html lang="km" data-bs-theme="light">
~~~
អាចដាក់ data-bs-theme="dark" លើ root ដើម្បីប្រើ dark mode ទូទាំង page ឬលើ container ដើម្បីអនុវត្តតែតំបន់មួយ:
~~~html
<div data-bs-theme="dark" class="p-4">
  <div class="card"><div class="card-body">មាតិកា dark</div></div>
</div>
~~~
Bootstrap 5.3 colors/modes អាច customize តាម Sass និង CSS variables។ សម្រាប់ element custom របស់យើងកំណត់ tokens ផ្ទាល់ និងភ្ជាប់ទៅ theme។

## Theme tokens ផ្ទាល់
~~~css
:root {
  --app-bg: #fff;
  --app-fg: #202124;
}
[data-bs-theme="dark"] {
  --app-bg: #121820;
  --app-fg: #f1f5f9;
}
body {
  background: var(--app-bg);
  color: var(--app-fg);
}
~~~
កុំ hardcode color ច្រើនកន្លែង; map UI ទាំងមូលទៅ tokens ដើម្បីប្តូរងាយ។

## User preference និង manual toggle
អាចចាប់ផ្តើមតាម prefers-color-scheme ហើយអនុញ្ញាត user toggle ដោយ JS; រក្សា preference ក្នុង localStorage ប្រសិនបើមានហេតុផល និងពន្យល់ behavior។ ប៊ូតុង toggle ត្រូវមាន accessible name និង state ត្រឹមត្រូវ។ កុំឱ្យ theme flash ខុសមុន JS ដំណើរការ ប្រសិនបើវាសំខាន់សម្រាប់ UX។

## Contrast និងរូបភាព
ត្រួតពិនិត្យ text, links, border, focus ring, alerts, form controls និង shadow លើ light/dark។ រូប logo/illustrations អាចមើលមិនឃើញលើ theme ផ្សេង—ប្រើ asset/variant ឬ background សម។ កុំសន្មតថាពណ៌ default Bootstrap ទាំងអស់មាន contrast គ្រប់ context។

## អនុវត្ត
បង្កើត theme toggle light/dark សម្រាប់ page មាន cards និង forms។ ប្រើ data-bs-theme និង CSS tokens សម្រាប់ custom elements។ សាក reload, keyboard, contrast និង color scheme system។

## សំណួរ
1. data-bs-theme="dark" អនុវត្តលើ element ណាខ្លះ?
2. ហេតុអ្វី custom UI គួរប្រើ CSS variables?
3. តើ theme toggle ត្រូវការអ្វីសម្រាប់ accessibility?

**ចម្លើយ**៖ element និង descendants ដែល Bootstrap/theme rules គាំទ្រ; tokens ជួយប្តូរពណ៌ស្របគ្នា; button មាន label/state ច្បាស់ និងអាចប្រើ keyboard។