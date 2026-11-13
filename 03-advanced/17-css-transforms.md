# មេរៀន ១៧៖ CSS Transforms

## គោលបំណង
បម្លែងទីតាំង, មុំ, ទំហំ និង perspective នៃ element ដោយមិនរៀប flow ដូច margin/position ទូទៅ។

## 2D transforms
~~~css
.move { transform: translate(1rem, -0.5rem); }
.rotate { transform: rotate(5deg); }
.scale { transform: scale(1.05); }
.skew { transform: skewX(-5deg); }
~~~
- translate ផ្លាស់ទី x/y; % ក្នុង translate គិតធៀប box របស់ element។
- rotate បង្វិល; deg ជាឯកតាមុំ។
- scale ពង្រីក/បង្រួម; តម្លៃ 1 ដើម, 0.9 តូច, 1.1 ធំ។
- skew បត់អ័ក្ស។
Transform មិនផ្លាស់ទីទីតាំងដើមក្នុង normal flow ទេ; អាច overlap ផ្នែកជិតខាង និងបង្កើត stacking context។

## Transform origin និង composition
~~~css
.icon {
  transform-origin: center;
  transform: rotate(12deg) scale(1.1);
}
~~~
transform-origin កំណត់ចំណុច pivot។ លំដាប់ functions ប៉ះពាល់លទ្ធផល ដូច្នេះសាកល្បងតាមលំដាប់។ Individual properties translate/rotate/scale មាននៅ browser modern ប៉ុន្តែ transform shorthand នៅតែមានប្រយោជន៍។

## 3D និង perspective
~~~css
.scene { perspective: 800px; }
.tile {
  transform: rotateY(20deg);
  transform-style: preserve-3d;
}
~~~
perspective ជួយបង្កើតជម្រៅ 3D; rotateX/rotateY/rotateZ បង្វិលតាមអ័ក្ស។ ប្រើ 3D ដោយមានគោលបំណង និងត្រូវគិត motion sickness, reduced-motion និងកុំឱ្យអត្ថបទអានពិបាក។

## Performance និង UX
ជាទូទៅ transform/opacity ល្អសម្រាប់ animation ជាងការប្តូរ width/left ដែលអាចបង្ក layout recalculation ប៉ុន្តែត្រូវវាស់នៅគម្រោងពិត។ កុំបន្ថែម will-change ជាអចិន្ត្រៃយ៍ទៅ element ច្រើន; វាប្រើធនធាន។

## អនុវត្ត
ធ្វើ card hover ឱ្យ translateY(-4px) និង scale(1.01) ជាមួយ transition។ ពិនិត្យថាមិនបាំង card ផ្សេង និងមាន focus-within state។

## លំហាត់
1. តើ transform ប្តូរ normal flow ដែរឬទេ?
2. transform-origin មានតួនាទីអ្វី?
3. តើ rotate(1turn) ស្មើនឹងអ្វី?

**ចម្លើយ**៖ មិនប្តូរ flow; កំណត់ pivot; បង្វិលមួយជុំ 360deg។