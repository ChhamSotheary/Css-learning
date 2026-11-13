# Chapter 16៖ Bootstrap JavaScript API

## គោលបំណង
ប្រើ data API ឬ JavaScript class API ដើម្បីគ្រប់គ្រង components ដែលត្រូវការ behavior។

## Data API
Attributes ដូច data-bs-toggle, data-bs-target, data-bs-dismiss ភ្ជាប់ HTML ទៅ Bootstrap plugin ដោយមិនសរសេរ JS initialization ច្រើន។ ត្រូវ load Bootstrap JS bundle; attributes មិនដំណើរការបើ JS មិន load ឬ selector ខុស។

## Class API
~~~js
const modalElement = document.getElementById('confirmModal');
const modal = new bootstrap.Modal(modalElement);
modal.show();
// បន្ទាប់មក
modal.hide();
~~~
API សមស្របពេលបើក modal បន្ទាប់ពី form validation, បង្ហាញ toast ក្រោយ save ឬគ្រប់គ្រង state តាម logic។ ពិនិត្យ component API/version ក្នុង official docs។ ប្រសិនបើ import ES modules ត្រូវ import class ឬ bundle ជារបៀបស្របគ្នា។

## Events និង lifecycle
Bootstrap plugins បញ្ចេញ events ដូច show/shown/hide/hidden។ អាចស្តាប់ event ដើម្បីធ្វើការបន្ទាប់ពី transition:
~~~js
modalElement.addEventListener('shown.bs.modal', () => {
  console.log('modal បានបង្ហាញ');
});
~~~
Event show/hide អាច prevent បានខ្លះៗ; shown/hidden កើតក្រោយ transition។ កុំ update DOM តាមការសន្មតថា transition ចប់ភ្លាម។

## Instance management
Bootstrap instance API ដូច getInstance/getOrCreateInstance/dispose អាចជួយក្នុង single-page apps។ Dispose plugin ពេល element ត្រូវបានដកចេញ ដើម្បីកុំទុក event listeners/resources។ កុំ initialize plugin ដដែលៗដោយគ្មានការគ្រប់គ្រង។

## Security និង trust
Bootstrap JS គ្រប់គ្រង UI ប៉ុណ្ណោះ; វាមិន validate permissions ឬ secure backend ទេ។ កុំបញ្ចូល HTML មិនទុកចិត្តចូល tooltip/popover/modal ដោយ innerHTML; sanitize/escape data តាម context។ Frontend controls អាច bypass បាន។

## អនុវត្ត
បើក modal ដោយ API បន្ទាប់ពី click button, ស្តាប់ shown event, ហើយ dispose instance នៅពេល remove។ ពិនិត្យ console និងកុំបើក modal មុន DOM ready។

## សំណួរ
1. Data API ត្រូវការអ្វីឱ្យ behavior ដំណើរការ?
2. shown.bs.modal ខុសពី show.bs.modal ត្រង់ណា?
3. Bootstrap JS ជំនួស authorization backend បានទេ?

**ចម្លើយ**៖ Bootstrap JS plugin ត្រូវ load និង target ត្រូវត្រឹមត្រូវ; show កើតពេលចាប់ផ្តើម, shown ក្រោយ transition; មិនបានទេ។