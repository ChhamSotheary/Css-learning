# Chapter 11៖ Dropdowns, Accordion និង Tabs

## Dropdown
~~~html
<div class="dropdown">
  <button class="btn btn-secondary dropdown-toggle" type="button"
          data-bs-toggle="dropdown" aria-expanded="false">
    ជម្រើស
  </button>
  <ul class="dropdown-menu">
    <li><a class="dropdown-item" href="/profile">គណនី</a></li>
    <li><button class="dropdown-item" type="button">ចេញ</button></li>
  </ul>
</div>
~~~
Dropdown ត្រូវ Bootstrap JavaScript និង Popper សម្រាប់ placement។ ប្រើ button ជា trigger; menu item អាច link សម្រាប់ navigation ឬ button សម្រាប់ action។ បញ្ជាក់ accessible label និងសាក keyboard navigation។ កុំដាក់ interactive control ច្រើនច្របូកក្នុង dropdown ដោយគ្មាន keyboard behavior។

## Accordion
Accordion ប្រើ Collapse plugin ដើម្បីបើក/បិទ content។ ប្រើ heading ជុំវិញ trigger button, aria-expanded, aria-controls និង target id។ បើមាន multiple panels កំណត់ id unique និង parent/behavior តាមគោលបំណង។ កុំប្រើ accordion លាក់មាតិកាសំខាន់ដែលអ្នកប្រើត្រូវប្រៀបធៀបញឹកញាប់។

## Tabs
Bootstrap tabs ប្រើ nav links/buttons ជាមួយ data-bs-toggle="tab" និង tab panes។ Tab interface ត្រូវយល់ role=tablist, role=tab, role=tabpanel, aria-selected, aria-controls និង keyboard arrow behavior។ Bootstrap Tab plugin ផ្តល់ behavior; ត្រូវរៀប markup តាម official example និងពិនិត្យ accessibility។ បើចង់ផ្លាស់ទំព័រ ប្រើ navigation links ធម្មតា មិនបន្លំជា tabs។

## Disclosure principles
Collapse/accordion/dropdown/tab ជា interface behavior; CSS class តែប៉ុណ្ណោះមិនគ្រប់គ្រាន់។ បើ JavaScript មិន load ត្រូវមើលថា content សំខាន់អាចចូលដល់បានឬអត់។ កុំដាក់ data-bs-* លើ element ខុស type។

## អនុវត្ត
បង្កើត FAQ accordion 3 សំណួរ និង dropdown menu។ បន្ថែម tabbed panel មួយតាម official markup; test keyboard, screen reader, no-JS fallback និង link/action semantics។

## សំណួរ
1. Dropdowns ត្រូវការ Popper ដែរឬទេ?
2. ហេតុអ្វី tab visual style មិនគ្រប់គ្រាន់?
3. Trigger របស់ accordion គួរដាក់ក្នុង heading ដែរឬទេ?

**ចម្លើយ**៖ Bootstrap dropdowns ប្រើ Popper សម្រាប់ positioning; tabs ត្រូវការ roles/state/keyboard behavior; គួរដាក់ button ក្នុង heading ដើម្បីរក្សា heading semantics។