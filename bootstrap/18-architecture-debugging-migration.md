# Chapter 18៖ Architecture, Debugging និង Migration

## CSS architecture
- កំណត់ design tokens សម្រាប់ color, spacing, radius និង typography។
- ប្រើ Bootstrap grid/utilities សម្រាប់ layout និង small adjustments។
- បង្កើត custom component class សម្រាប់ repeated patterns ដូច profile-card។
- ដាក់ custom overrides ក្រោយ Bootstrap CSS ឬប្រើ Sass variables/CSS variables ដោយចេតនា។
- កុំកែ bootstrap.min.css ផ្ទាល់ និងកុំប្រើ important ជាដំណោះស្រាយ default។
- កត់ត្រា convention: utilities vs component CSS, breakpoints, theme, RTL support។

## Debugging class ដែលមិនដំណើរការ
1. ពិនិត្យ Bootstrap version ក្នុង CDN/package។
2. DevTools Network: CSS/JS ត្រូវបាន load ឬអត់? status/URL ត្រឹមត្រូវ?
3. Inspect element: class typo? class ត្រូវនឹង version?
4. Computed styles: rule ត្រូវបាន override ដោយ selector/order/layer ណា?
5. Components: JS plugin ត្រូវបាន load? data-bs-target id ត្រូវគ្នា?
6. Console: error ឬ Popper missing?
7. Responsive: breakpoint ដែលអ្នកសាកល្បងឆ្លង threshold ឬនៅ?

## Migration
ពេលប្តូរ Bootstrap major version កុំធ្វើ find-and-replace class ទាំងអស់ភ្លាម។ អាន official migration guide, ស្វែងរក breaking changes, សាក components និង utilities ដែលប្រើ, ពិនិត្យ JS APIs/data attributes, update Sass overrides, run visual/accessibility checks។ កុំយក docs v4 ជាមួយ code v5 ឬផ្ទុយគ្នា។

## RTL និងភាសាច្រើន
Bootstrap មាន RTL stylesheet build សម្រាប់ workflow ជាក់លាក់; ត្រូវជ្រើស CSS file ត្រឹមត្រូវ និងសាក logical utilities, icons, navbar alignment។ អត្ថបទខ្មែរ LTR ជាទូទៅ ប៉ុន្តែ multilingual app អាចមាន RTL។ ប្រើ start/end naming នៅកន្លែងសមស្រប និងសាក layout ទិសផ្សេង។

## អនុវត្តចុងវគ្គ
ជ្រើស project មួយពី Projects។ រៀបចំ source/build, custom theme, reusable components, responsive layout, keyboard/accessibility checks និង README របៀប run។ បន្ទាប់មកបង្កើត checklist ពេល update Bootstrap minor/major version។

## សំណួរ
1. តើជំហានដំបូងពេល class មិនដំណើរការគឺអ្វី?
2. ហេតុអ្វីមិនគួរ migrate ដោយ replace class ឆៅ?
3. តើ Sass variables/utility overrides គួររក្សាទុកកន្លែងណា?

**ចម្លើយ**៖ ពិនិត្យ version និង asset load; major versions អាចមាន breaking CSS/JS/API changes; រក្សា source custom ក្នុង project files ហើយ rebuild ជំនួសការកែ compiled Bootstrap។