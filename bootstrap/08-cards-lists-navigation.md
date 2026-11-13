# Chapter 08៖ Cards, List Groups និង Navigation Helpers

## Cards
~~~html
<article class="card h-100">
  <img src="course.jpg" class="card-img-top" alt="">
  <div class="card-body">
    <h2 class="card-title h5">វគ្គ HTML</h2>
    <p class="card-text">រៀនបង្កើតគេហទំព័រមូលដ្ឋាន។</p>
    <a href="/courses/html" class="btn btn-primary">មើលមេរៀន</a>
  </div>
</article>
~~~
Card ជា container flexible; អាចមាន image/header/body/footer។ h-100 អាចធ្វើឱ្យ cards កម្ពស់ស្មើក្នុង grid row តែត្រូវពិនិត្យ content។ កុំធ្វើ card ទាំងមូល clickable ដោយដាក់ link nested ជាច្រើន; បង្កើត interaction ត្រឹមត្រូវ។

## List groups
~~~html
<ul class="list-group">
  <li class="list-group-item d-flex justify-content-between align-items-center">
    សារ <span class="badge text-bg-primary rounded-pill">3</span>
  </li>
</ul>
~~~
List group សម្រាប់បញ្ជីធាតុ; links/buttons អាចប្រើជា actionable items។ ប្រសិនបើជា navigation ពិត ប្រើ <nav> និង link semantics ផងដែរ។

## Breadcrumb និង pagination
Breadcrumb បង្ហាញទីតាំងក្នុង hierarchy; navigation មាន aria-label, item បច្ចុប្បន្នអាច aria-current="page"។ Pagination ប្រើ nav/list/link ហើយបង្ហាញ disabled/current states ដោយ accessible attributes។

## Nav tabs/pills (presentation មិនស្មើ behavior)
~~~html
<ul class="nav nav-pills">
  <li class="nav-item"><a class="nav-link active" aria-current="page" href="/overview">ទិដ្ឋភាពទូទៅ</a></li>
  <li class="nav-item"><a class="nav-link" href="/details">ព័ត៌មានលម្អិត</a></li>
</ul>
~~~
Nav links សម្រាប់ផ្លាស់ទំព័រ; tab interface ដែលប្តូរ content នៅទំព័រដដែលត្រូវមាន tab roles, keyboard behavior និង Bootstrap Tab JS ឬ implementation ដែលស្រប accessibility pattern។

## អនុវត្ត
បង្កើត course catalog 6 cards ក្នុង grid; បន្ថែម breadcrumb និង pagination ដែលមាន aria-current។ សាកអត្ថបទចំណងជើងវែង និងគ្រប់ link ដោយ keyboard។

## សំណួរ
1. Card ជួយអ្វី?
2. Breadcrumb បង្ហាញអ្វី?
3. តើ nav-pills ធ្វើឱ្យ content tab ប្តូរដោយស្វ័យប្រវត្តិទេ?

**ចម្លើយ**៖ រៀប content related ជា block; ទីតាំងក្នុង hierarchy; ទេ—visual class មិនបង្កើត behavior។