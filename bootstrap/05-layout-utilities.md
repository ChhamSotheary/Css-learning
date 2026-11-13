# Chapter 05៖ Spacing, Sizing, Display និង Flex Utilities

## គោលបំណង
ប្រើ Bootstrap utility classes ដើម្បីកែ spacing, width, display និង alignment ដោយមិនសរសេរ CSS រាល់ចំណុច។

## Spacing utilities
ទម្រង់៖ property + side + breakpoint optional + scale។ ឧទាហរណ៍ **mt-3** (margin-top), **px-4** (padding ឆ្វេង/ស្តាំ), **mb-lg-0** (margin-bottom ត្រូវសូន្យនៅ lg ឡើង), **gap-2** (gap)។ Bootstrap 5 ប្រើ logical naming ខ្លះ ដូច **ms-*** (margin-start), **me-*** (margin-end), **ps-***, **pe-*** ដើម្បីគាំទ្រ writing direction។

Scale default មាន 0–5 និង auto សម្រាប់ margin; តម្លៃទាក់ទងទៅ Sass spacer scale (ជាធម្មតា 0.25rem increments, 1 = 0.25rem, 3 = 1rem, 5 = 3rem)។ Scale អាច customize បាន។ កុំសន្មត scale នេះនៅ project ដែលបានកែ Sass។

## Sizing និង display
~~~html
<div class="w-100">ទទឹងពេញ parent</div>
<div class="min-vh-100">កម្ពស់អប្បបរមាតាម viewport</div>
<div class="d-none d-md-block">បង្ហាញចាប់ពី md</div>
~~~
Utilities ដូច w-*, h-*, min-vh-*, mw-100 កំណត់ទំហំ; **d-*** ប្ដូរ display។ display:none លាក់ពី layout, ដូច្នេះកុំបិទ content សំខាន់ដោយគ្មាន alternative។

## Flex utilities
~~~html
<div class="d-flex flex-column flex-md-row align-items-md-center justify-content-between gap-3">
  <h2 class="mb-0">ចំណងជើង</h2>
  <a class="btn btn-primary" href="#">ស្វែងយល់</a>
</div>
~~~
**d-flex** បង្កើត flex container; **flex-column/row** កំណត់ទិស; **justify-content-*** main axis; **align-items-*** cross axis; **flex-wrap** អនុញ្ញាត wrap; **gap-*** ចន្លោះ items។ Bootstrap utilities ជា classes; ត្រូវស្គាល់ Flexbox មូលដ្ឋានដើម្បីយល់លទ្ធផល។

## Text alignment, float និង vertical align
text alignment អាចមាន breakpoint variant; float គួរប្រើតាមតួនាទី content មិនមែនសម្រាប់ layout ទាំងមូល។ vertical-align ប្រើលើ inline/table-cell context មិនមែនកណ្ដាល div ធម្មតាទេ។ ប្រើ flex/grid សម្រាប់ alignment ទូទៅ។

## អនុវត្ត
បង្កើត hero row ដែល stack vertically លើទំហំតូច និងជា row នៅ md; ប្រើ gap, spacing, text alignment utilities។ ពន្យល់ថា class នីមួយៗប៉ះ property/axis ណា។

## សំណួរ
1. ms-3 មានន័យអ្វី?
2. d-md-none អនុវត្តពី breakpoint ណា?
3. justify-content កែអ័ក្សណាក្នុង flex?

**ចម្លើយ**៖ margin-start scale 3; លាក់ពី md ឡើងទៅ; main axis។