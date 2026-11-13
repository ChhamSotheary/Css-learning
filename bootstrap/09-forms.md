# Chapter 09៖ Forms និង Validation States

## Form group
~~~html
<form>
  <div class="mb-3">
    <label for="email" class="form-label">អ៊ីមែល</label>
    <input id="email" class="form-control" type="email"
           autocomplete="email" required>
    <div class="form-text">យើងប្រើអ៊ីមែលសម្រាប់ទាក់ទងប៉ុណ្ណោះ។</div>
  </div>
  <button class="btn btn-primary" type="submit">ផ្ញើ</button>
</form>
~~~
label for ត្រូវតែដូច id។ Placeholder មិនមែនជា label។ form-control style text inputs; form-select style select; form-check សម្រាប់ checkbox/radio; input-group ភ្ជាប់ addon ដូចរូបិយប័ណ្ណ។ ប្រើ autocomplete/input type ត្រឹមត្រូវ ដើម្បីជួយទូរស័ព្ទនិង password managers។

## Validation
Bootstrap ផ្តល់ :valid/:invalid styles និង .is-valid/.is-invalid classes។ HTML attributes ដូច required, type=email, min/max ជួយ native validation; server ត្រូវ validate ម្តងទៀត—client-side មិនមែន security boundary ទេ។

~~~html
<div class="mb-3">
  <label for="name" class="form-label">ឈ្មោះ</label>
  <input id="name" class="form-control is-invalid" aria-describedby="name-error" required>
  <div id="name-error" class="invalid-feedback">សូមបញ្ចូលឈ្មោះ។</div>
</div>
~~~
Error text ត្រូវភ្ជាប់ដោយ aria-describedby, បង្ហាញថា field ណាខុស និងវិធីកែ។ Bootstrap validation custom style អាចប្រើ JS class; កុំបង្ហាញ error ពណ៌តែមួយ។

## Form layouts
Grid/row/col រៀប fields; col-form-label តម្រឹម horizontal form; row g-* គ្រប់គ្រង gap។ Mobile-first សូម stack fields មុន។ form-floating ប្រើ placeholder style ក្នុង input តែ label ត្រូវនៅក្នុង markup ដូច docs និងត្រូវសាក Khmer text (label វែងអាចលើសកន្លែង)។

## អនុវត្ត
បង្កើត registration form មាន name, email, password, select, checkbox និង error state។ ពិនិត្យ label associations, required, keyboard, zoom និង error message។

## សំណួរ
1. ហេតុអ្វី placeholder មិនជំនួស label?
2. តើ class is-invalid ធ្វើឱ្យ form validate នៅ server ទេ?
3. តើ error message ត្រូវភ្ជាប់ field ដូចម្តេច?

**ចម្លើយ**៖ placeholder បាត់ពេលបញ្ចូល ហើយមិនមាន label ដដែល; មិនទេ—server ត្រូវ validate; ប្រើ aria-describedby ទៅ id របស់ error message។