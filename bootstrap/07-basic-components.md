# Chapter 07៖ Buttons, Badges, Alerts និង Progress

## Buttons
~~~html
<button type="button" class="btn btn-primary">រក្សាទុក</button>
<a class="btn btn-outline-secondary" href="/help">ជំនួយ</a>
<button type="button" class="btn btn-danger" disabled>លុប</button>
~~~
.btn ជា base; btn-primary/secondary/success/danger/... កំណត់ variant; btn-outline-* ជា outline variant; btn-lg/sm ទំហំ។ ប្រើ <button> សម្រាប់ action និង <a> សម្រាប់ navigation។ Anchor button ត្រូវមាន href ពិត មិនមែនទទេ។ Disabled state ត្រូវដំណើរការតាម HTML disabled លើ button មិនមែនពណ៌ស្រាលតែប៉ុណ្ណោះ។

## Button groups
Button group រៀប buttons ដែលមានទំនាក់ទំនង។ ប្រើ role/ARIA តាម pattern និង label group ពេលចាំបាច់។ Toggle buttons ត្រូវភ្ជាប់ state ទៅ input/JS ត្រឹមត្រូវ; visual style មិនមានន័យថា state ដំណើរការទេ។

## Badges
~~~html
<h2>សារថ្មី <span class="badge text-bg-secondary">4</span></h2>
~~~
Badge បង្ហាញ count/status សង្ខេប។ ប្រសិនបើលេខតែមួយមិនមានន័យសម្រាប់ screen reader បន្ថែម visually-hidden text។

## Alerts
~~~html
<div class="alert alert-warning" role="alert">
  <h2 class="h5">សូមពិនិត្យទិន្នន័យ</h2>
  <p class="mb-0">ថ្ងៃផុតកំណត់ត្រូវបានទុកទទេ។</p>
</div>
~~~
alert variant មាន info/success/warning/danger។ role=alert គួរប្រើសម្រាប់សារសំខាន់ដែលត្រូវប្រកាសភ្លាម; កុំដាក់លើសារទាំងអស់បើវាបង្ករំខាន។ Dismissible alert ត្រូវការជំនួយ JavaScript និងប៊ូតុង close មាន accessible label។

## Progress bars
~~~html
<div class="progress" role="progressbar"
     aria-label="វឌ្ឍនភាពការទាញយក"
     aria-valuenow="65" aria-valuemin="0" aria-valuemax="100">
  <div class="progress-bar" style="width: 65%">65%</div>
</div>
~~~
បច្ចុប្បន្នភាព aria-valuenow ត្រូវស្របនឹង width ពិត (ធ្វើដោយ JS សម្រាប់ dynamic progress)។ កុំប្រើ progress bar ជំនួសពាក្យពន្យល់ state។

## អនុវត្ត
បង្កើត form status panel មាន success alert, badge ចំនួន notification, action buttons និង progress bar។ សាក keyboard និង screen reader labels។

## សំណួរ
1. <a class="btn"> និង <button class="btn"> តួនាទីខុសគ្នាដូចម្តេច?
2. តើ alert role គួរប្រើគ្រប់ករណីទេ?
3. តើ progress bar គួរធ្វើបច្ចុប្បន្នភាពអ្វីខ្លះពេល JS ប្តូរតម្លៃ?

**ចម្លើយ**៖ link navigate, button action; ទេ ប្រើតាមភាពបន្ទាន់; width/text និង aria-valuenow ត្រូវស្របគ្នា។