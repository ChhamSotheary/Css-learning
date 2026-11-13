# Chapter 06៖ Colors, Typography, Images និង Tables

## Colors និង semantic meaning
Bootstrap មាន theme colors ដូច primary, secondary, success, danger, warning, info, light, dark និង text/body emphasis utilities។ ឧទាហរណ៍ **text-bg-primary**, **text-danger**, **bg-body-tertiary** (សូមពិនិត្យ class តាម version)។ កុំប្រើពណ៌តែមួយដើម្បីបញ្ជាក់ error/success; បន្ថែម icon/text/state។

~~~html
<div class="p-3 text-bg-primary">ផ្ទៃពណ៌ primary</div>
<p class="text-body-secondary">ព័ត៌មានបន្ថែម</p>
~~~
Colors/theme tokens អាចប្តូរតាម Sass ឬ CSS variables។ ពិនិត្យ contrast ជាពិសេស warning/light backgrounds និងអក្សរតូច។

## Images និង figures
~~~html
<img src="photo.jpg" class="img-fluid rounded" alt="ទេសភាពភ្នំ">
~~~
**img-fluid** ធ្វើឱ្យ image max-width:100% និង height:auto។ **rounded**, **rounded-circle** ជារូបរាង។ **figure/figcaption** បន្ថែមអត្ថន័យ caption; alt ពិពណ៌នាគោលបំណងរូប មិនចាំបាច់ពណ៌នារាល់លម្អិត។

## Tables
~~~html
<div class="table-responsive">
  <table class="table table-striped table-hover align-middle">
    <caption class="caption-top">បញ្ជីសិស្ស</caption>
    <thead>
      <tr><th scope="col">ឈ្មោះ</th><th scope="col">ពិន្ទុ</th></tr>
    </thead>
    <tbody>
      <tr><th scope="row">សុភា</th><td>90</td></tr>
    </tbody>
  </table>
</div>
~~~
.table ផ្តល់ base style; table-striped/table-hover បន្ថែម visual treatment; table-responsive ឱ្យ horizontal scroll នៅ viewport តូច។ Header cells ត្រូវមាន scope ដើម្បីជួយការអានតារាង។ កុំប្រើ table សម្រាប់ page layout។

## Khmer typography
កំណត់ font stack ដោយ custom stylesheet ហើយពិនិត្យ line-height, text wrapping, buttons និង table cells។ កុំកំណត់ height ថេរដល់ row ដែលមានអត្ថបទខ្មែរ ព្រោះ line wrapping/combining marks អាចបង្កកាត់ content។

## អនុវត្ត
បង្កើត article មាន color hierarchy, responsive image, caption និង table មាន caption + scopes។ សាកទទឹងតូច និង high contrast mode។

## សំណួរ
1. img-fluid ធ្វើអ្វី?
2. តើ table-responsive ជួយអ្វី?
3. ហេតុអ្វីមិនគួរប្រើតែពណ៌ក្រហមសម្រាប់ error?

**ចម្លើយ**៖ image មិនលើស parent និងរក្សា ratio; wrapper អនុញ្ញាត scroll នៅទទឹងតូច; អ្នកមាន color vision deficiency អាចមិនសម្គាល់បាន ដូច្នេះបន្ថែម text/icon។