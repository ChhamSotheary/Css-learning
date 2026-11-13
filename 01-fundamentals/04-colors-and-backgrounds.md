# មេរៀន ៤៖ ពណ៌ និង Background

## គោលបំណង
សរសេរពណ៌ដោយទម្រង់ផ្សេងៗ និងគ្រប់គ្រង background color/image ដោយមិនធ្វើឱ្យអត្ថបទអានមិនច្បាស់។

## ទម្រង់ពណ៌
~~~css
.box { color: navy; }                 /* ឈ្មោះ */
.box { color: #14532d; }              /* HEX */
.box { color: rgb(20 83 45); }        /* RGB */
.box { color: rgb(20 83 45 / 70%); }  /* RGB + alpha */
.box { color: hsl(142 61% 30%); }     /* HSL */
.box { color: hsl(142 61% 30% / 0.7); } /* HSLA alpha */
~~~
HEX សមស្របសម្រាប់ palette ថេរ; RGB/HSL អាចកែ channel ឬ transparency បានងាយ។ Alpha 0 មានតម្លាភាព, 1 ឬ 100% មិនថ្លា។

## Background image
~~~css
.hero {
  background-color: #123;
  background-image: url("../images/hero.jpg");
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}
~~~
**cover** បំពេញប្រអប់ទាំងមូល ហើយអាច crop រូប; **contain** បង្ហាញរូបទាំងមូល ប៉ុន្តែអាចនៅសល់ចន្លោះ។ background-repeat អាចជា repeat, repeat-x, repeat-y, no-repeat។ background-position គាំទ្រពាក្យ center, top, left និងតម្លៃផ្សេងៗ។

## Shorthand
~~~css
.hero {
  background: #123 url("../images/hero.jpg") center / cover no-repeat;
}
~~~
លំដាប់ background shorthand អាចសរសេរ color, image, position/size, repeat ជាដើម។ ប្រើ longhand ដំបូងដើម្បីយល់; shorthand ពេលអានកូដស្រួល។

**background-attachment: fixed** ធ្វើឱ្យ background មើលទៅជាប់ viewport នៅ context ខ្លះៗ ប៉ុន្តែឥរិយាបថ mobile/browser អាចខុសគ្នា; កុំទុកចិត្តលើវាសម្រាប់ content សំខាន់។

## Contrast និង accessibility
ត្រូវរក្សា contrast អក្សរ/ផ្ទៃឱ្យអានច្បាស់។ កុំប្រើ background image ជំនួសអត្ថបទសំខាន់; រក្សា fallback color ហើយកុំបន្ថយ opacity លើ parent ដើម្បីធ្វើឱ្យតែផ្ទៃស្រអាប់ (វាធ្វើឱ្យកូនទាំងអស់ស្រអាប់)។ ប្រើ overlay ឬ color តម្លាភាពជំនួស។

## អនុវត្ត
បង្កើត hero 300px មាន image, cover, center និង fallback background។ បន្ថែម overlay ពណ៌ខ្មៅស្រាល ហើយធ្វើឱ្យចំណងជើងអានបាន។

## សំណួរ
1. cover និង contain ខុសគ្នាយ៉ាងដូចម្តេច?
2. តើ alpha ក្នុង rgba/hsl មានតួនាទីអ្វី?
3. ហេតុអ្វីត្រូវមាន background-color បម្រុង?

**ចម្លើយ**៖ cover អាច crop ដើម្បីពេញ; contain បង្ហាញរូបទាំងមូល; alpha គ្រប់គ្រងភាពថ្លា; fallback បង្ហាញពេលរូបមិន load និងធានា contrast។