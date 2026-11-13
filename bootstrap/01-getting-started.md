# Chapter 01៖ Bootstrap ជាអ្វី និងការដំឡើង

## ១. Bootstrap ជាអ្វី?
Bootstrap ជា frontend toolkit មាន CSS styles, layout utilities, responsive grid និង JavaScript components។ វាជួយឱ្យបង្កើត interface បានលឿនដោយប្រើ class ដែលមានស្រាប់។ Bootstrap មិនមែនជា language ថ្មី និងមិនបង្កើត website ដោយស្វ័យប្រវត្តិទេ—អ្នកនៅតែត្រូវសរសេរ HTML, ជ្រើស design និងបន្ថែម CSS/JavaScript តាមតម្រូវការ។

Bootstrap 5.3.9 ជាកំណែគោលរបស់មេរៀននេះ។ Bootstrap 5 មិនត្រូវការ jQuery។ សូមមើល official docs មុនប្តូរ version ព្រោះ CDN URL និង SRI hash ត្រូវផ្គូផ្គងគ្នា។

## ២. មូលដ្ឋាន HTML
Bootstrap គ្រប់គ្រង responsive layout ត្រូវការ doctype និង viewport meta៖
~~~html
<!doctype html>
<html lang="km">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>រៀន Bootstrap</title>
</head>
<body>
  <h1>សួស្តី Bootstrap</h1>
</body>
</html>
~~~
- doctype ប្រាប់ browser render ជា standards mode។
- charset UTF-8 គាំទ្រអក្សរខ្មែរ។
- viewport meta ឱ្យទទឹង layout តាមឧបករណ៍ mobile។
- lang="km" ជួយ screen reader និង search engine ស្គាល់ភាសាទំព័រ។

## ៣. ដាក់ Bootstrap ដោយ CDN
យក CSS link, JS bundle, version និង integrity ពី official docs។ ទម្រង់សង្ខេប៖
~~~html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.9/dist/css/bootstrap.min.css"
      rel="stylesheet">
~~~
ដាក់ link ក្នុង head។ សម្រាប់ components ដែលប្រើ JavaScript ដាក់ bundle មុន </body>៖
~~~html
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.9/dist/js/bootstrap.bundle.min.js"></script>
~~~
ឧទាហរណ៍បង្ហាញ URL ទម្រង់ប៉ុណ្ណោះ; សម្រាប់ deployment សូមយក snippet ពេញពី official docs រួម integrity/crossorigin ដែលត្រូវនឹង version។ Bundle មាន Popper សម្រាប់ dropdown, popover និង tooltip។ បើត្រូវការ CSS/JS ពេល offline ត្រូវដំឡើង local package (មេរៀន 14)។

## ៤. Class ដំបូង
~~~html
<main class="container py-5">
  <h1 class="text-primary">ស្វាគមន៍</h1>
  <p class="lead">នេះជាទំព័រ Bootstrap ដំបូង។</p>
  <button class="btn btn-primary">ចាប់ផ្តើម</button>
</main>
~~~
container កំណត់ width/centering, py-5 ជា padding block-axis, text-primary ជា color token, btn និង btn-primary ជា component classes។

## ៥. របៀបរៀនដោយមិនពឹង class ដោយចៃដន្យ
ពេលឃើញ class មួយ សួរ៖ property អ្វីដែលវាប៉ះ? breakpoint ណា? តើវាផ្លាស់ DOM behavior ឬតែរូបរាង? ប្រើ DevTools inspect computed CSS និងឯកសារ Utilities/Components។ កុំយក class ពី version ផ្សេងមកចម្លងដោយមិនពិនិត្យ។

## អនុវត្ត
បង្កើត index.html, ភ្ជាប់ Bootstrap CSS ហើយធ្វើ page មាន h1, paragraph, primary button។ កំណត់ lang="km", UTF-8 និង viewport។ សាកដក stylesheet ចេញដើម្បីប្រៀបធៀប។

## ពិនិត្យខ្លួនឯង
1. Bootstrap ជំនួស HTML/CSS ឬទេ?
2. Viewport meta ជួយអ្វី?
3. តើ jQuery ត្រូវការក្នុង Bootstrap 5 ដែរឬទេ?
4. ហេតុអ្វី integrity hash ត្រូវផ្គូផ្គង version?

**ចម្លើយ**៖ មិនជំនួសទេ; viewport ធ្វើឱ្យ layout មានទំហំសមនឹង mobile; Bootstrap 5 មិនត្រូវការ jQuery; hash ផ្ទៀងផ្ទាត់ resource ហើយ hash ខុសនឹងធ្វើឱ្យ browser បដិសេធ file។