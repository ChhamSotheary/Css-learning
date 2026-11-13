# Chapter 10៖ Navbar, Collapse និង Offcanvas

## Responsive navbar
Navbar មាន navigation brand, links, dropdowns និង responsive collapse។ Navbar CSS classes មិនទាន់មាន behavior collapse បើ JS plugin មិន load ទេ។

~~~html
<nav class="navbar navbar-expand-lg bg-body-tertiary">
  <div class="container">
    <a class="navbar-brand" href="/">សាលារៀន</a>
    <button class="navbar-toggler" type="button"
            data-bs-toggle="collapse" data-bs-target="#mainNav"
            aria-controls="mainNav" aria-expanded="false"
            aria-label="បើកឬបិទម៉ឺនុយ">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="mainNav">
      <ul class="navbar-nav ms-auto">
        <li class="nav-item"><a class="nav-link active" aria-current="page" href="/">ទំព័រដើម</a></li>
      </ul>
    </div>
  </div>
</nav>
~~~
navbar-expand-lg មានន័យថា navbar ពង្រីកជា horizontal ចាប់ពី lg; មុន lg toggler បើក collapse។ target id ក្នុង data-bs-target ត្រូវផ្គូផ្គង id តែមួយ។ aria-expanded state ត្រូវ update ដោយ plugin។

## Collapse ដោយឡែក
data-bs-toggle="collapse" និង data-bs-target="#panel" បើក/បិទ panel; button ត្រូវមាន aria-controls និង aria-expanded ដំបូងសមស្រប។ សម្រាប់ content ដែលលាក់, កុំដាក់ focusable controls ក្នុង state លាក់ដែលនៅអាច focus បាន; Bootstrap collapse គ្រប់គ្រង display behavior។

## Offcanvas
Offcanvas ជា panel លេចពីគែម សម្រាប់ navigation/sidebar។ ប្រើ button data-bs-toggle="offcanvas", data-bs-target, dialog/label semantics និង close control។ ពិនិត្យ keyboard focus, Escape, backdrop, scrolling និង focus return ដោយសាកល្បងពិត។

## Accessibility checks
- Toggler ជា button ពិត មាន accessible name។
- aria-controls សំដៅទៅ target មាន id។
- aria-expanded បង្ហាញស្ថានភាព។
- Link មាន text ពិពណ៌នា; active page អាចដាក់ aria-current។
- កុំធ្វើ hover-only menu; touch/keyboard ត្រូវអាចប្រើ។

## អនុវត្ត
បង្កើត navbar ដែលលាក់ links នៅ mobile និងបង្ហាញពី lg; បង្កើត offcanvas menu សម្រាប់ mobile navigation។ Test tab, Enter, Space, Escape និង screen reader label។

## សំណួរ
1. navbar-expand-lg មានន័យអ្វី?
2. data-bs-target ត្រូវផ្គូផ្គងអ្វី?
3. តើ CSS តែមួយអាចធ្វើ collapse behavior ដែរឬទេ?

**ចម្លើយ**៖ expand ចាប់ពី lg; id របស់ target; មិនទេ, Bootstrap JS plugin គ្រប់គ្រង toggle behavior។