# មេរៀន ១១៖ Flexbox

## គោលបំណង
ប្រើ Flexbox សម្រាប់រៀបចំ items តាមអ័ក្សមួយ និងគ្រប់គ្រង spacing, alignment និងការរីក/រួម។

## Container និង axes
~~~css
.toolbar {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
}
~~~
Main axis តាម flex-direction; cross axis កាត់វា។ row ជួរដេក (default), column ជួរឈរ។ **justify-content** គ្រប់គ្រង main axis; **align-items** គ្រប់គ្រង cross axis។ align-content គ្រប់គ្រងបន្ទាត់ច្រើនពេលមាន wrap និងមានកន្លែងទំនេរ; វាមិនដូច align-items ទេ។

## Flex items
~~~css
.item { flex: 1 1 12rem; }
.item--fixed { flex: 0 0 8rem; }
.special { align-self: flex-start; }
~~~
flex shorthand គឺ grow, shrink, basis។ **flex-grow** ចែកកន្លែងបន្ថែម; **flex-shrink** អនុញ្ញាតរួមពេលមិនគ្រប់; **flex-basis** ជាទំហំមូលដ្ឋានមុនចែកចន្លោះ។ **order** ប្តូរលំដាប់មើលឃើញ តែ DOM/keyboard order មិនប្តូរតាម; ប្រើដោយប្រុងប្រយ័ត្នសម្រាប់ accessibility។

## គំរូ navigation
~~~css
.nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
}
.nav__links { display: flex; flex-wrap: wrap; gap: 0.75rem; }
~~~
ប្រើ gap ជំនួស margin trick ច្រើន។ សម្រាប់ content ដែលមានពីរវិមាត្រ/ជួរឈរច្រើន CSS Grid អាចសមជាង។

## Debugging
បើ child រុញលើស container សាក **min-width:0** លើ flex child និងកំណត់ overflow-wrap លើអត្ថបទវែង។ ចងចាំ flex item មាន min-width:auto ជាទូទៅ ដែលអាចរក្សាទទឹង content ធំបំផុត។

## អនុវត្ត
បង្កើត header មាន logo ខាងឆ្វេង និង navigation ខាងស្តាំ; បើទទឹងតូច links wrap ទៅបន្ទាត់ថ្មី។ បង្កើត row នៃ cards ដែល flex-basis 16rem និង gap 1rem។

## ពិនិត្យខ្លួនឯង
1. justify-content គ្រប់គ្រងអ័ក្សណា?
2. flex-basis ជាអ្វី?
3. តើ order ប្តូរ DOM order ដែរឬទេ?

**ចម្លើយ**៖ main axis; ទំហំគោលរបស់ item; មិនប្តូរ DOM order ទេ។