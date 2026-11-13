# Chapter 03៖ Containers និង Breakpoints

## Containers
Container កំណត់កន្លែងទំព័រ និងផ្តល់ horizontal padding។ វាមានសារៈសំខាន់ជាពិសេសជាមួយ grid។ ជម្រើស៖
- **.container**: width/max-width តាម breakpoint។
- **.container-fluid**: ទទឹង 100% គ្រប់ viewport។
- **.container-{breakpoint}**: ពេញទទឹងរហូតដល់ breakpoint មួយ រួចកំណត់ max-width តាមជំហាន។

~~~html
<main class="container">
  <section class="py-4">Content មានទទឹងអានងាយ</section>
</main>
~~~

## Breakpoints mobile-first
Bootstrap 5.3 default breakpoints៖ xs (តូចបំផុត, គ្មាន prefix), sm 576px, md 768px, lg 992px, xl 1200px, xxl 1400px។ Class ដូច **d-md-flex** ចាប់ពី md ឡើងទៅ ហើយបន្តទៅ breakpoint ធំៗ។ Breakpoints គិតតាម min-width media queries ដូច្នេះ class មិនមែនមានន័យថា «តែទំហំ md» ទេ។

Container max-width តាម defaults៖ sm 540px, md 720px, lg 960px, xl 1140px, xxl 1320px។ តម្លៃនេះអាចប្ដូរបានតាម Sass configuration; ពិនិត្យ docs កំណែដែលប្រើ។

## Responsive utility
~~~html
<div class="d-none d-md-block">បង្ហាញចាប់ពី md ឡើងទៅ</div>
<div class="text-center text-lg-start">កណ្តាលលើទំហំតូច; start នៅ lg+</div>
~~~
ការលាក់ element ត្រូវពិចារណា accessibility និង content: កុំលាក់ link/navigation សំខាន់ដោយគ្មានវិធីចូលដល់។

## ជ្រើស breakpoint
ជ្រើសពេល content/card/navigation មិនសមទៀត មិនមែនសន្មតថា «ទូរស័ព្ទ = 576» ទាំងអស់។ សាកល្បងទទឹងជាប់ breakpoint និងអត្ថបទខ្មែរវែងៗ; breakpoints អាចជាលេខកំណត់ទុកមុន ប៉ុន្តែ design ត្រូវសមនឹង content។

## អនុវត្ត
បង្កើត container សម្រាប់ article, ប្រៀបធៀប container និង container-fluid, កំណត់ title align តាម breakpoint។ សាកចន្លោះ 575/576, 767/768 និងទំហំច្រើនទៀត។

## សំណួរ
1. .container និង .container-fluid ខុសគ្នាដូចម្តេច?
2. .col-md-* ឬ d-md-* ចាប់ផ្តើមពីទំហំអ្វី?
3. ហេតុអ្វី breakpoint គួរជ្រើសតាម content?

**ចម្លើយ**៖ container កំណត់ max-width តាម tier; fluid ពេញ 100%; md ចាប់ពី 768px នៅ default; content មានប្រវែង/ទំហំខុសគ្នាតាម layout។