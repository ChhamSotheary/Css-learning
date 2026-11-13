# Project 3៖ Fashion E-commerce UI

**កម្រិត៖ Advanced**  
**មេរៀនពាក់ព័ន្ធ៖** 13–18 និង 20–21

## គោលបំណង
បង្កើត storefront UI សម្រាប់មើលផលិតផល៖ navigation, category controls, product grid, product cards, price, badge និង interaction states។

## តម្រូវការ
- Product grid បត់បែនដោយ repeat/minmax ឬ media queries។
- Card មាន image ratio ស្ថិរភាព, title, price និង link/action ច្បាស់។
- ប្រើ pseudo-class សម្រាប់ hover/focus/checked state តាមការសម។
- ប្រើ pseudo-elements តែសម្រាប់ decoration មិនមែនព័ត៌មានចាំបាច់។
- Transition/transform ស្រាល និងគោរព prefers-reduced-motion។
- Category filter ជា checkbox/button semantic; UI state ពិតត្រូវប្រើ functionality ដែលសម។
- សាក product title វែង, រូបភាពខុស ratio និងទំហំទូរស័ព្ទ។

## ជំហាន
1. កំណត់ tokens សម្រាប់ brand, neutral, spacing និង radius។
2. សរសេរ product data ក្នុង HTML ដោយ semantic articles។
3. កំណត់ grid responsive និង image object-fit។
4. បន្ថែម card states និង interaction focus។
5. បន្ថែម motion តិចៗ និង reduced-motion alternative។
6. ពិនិត្យ contrast, keyboard order, labels និង responsive behavior។

## Checklist
- [ ] Product image មិនបំភ្លៃសមាមាត្រ។
- [ ] Focus មើលឃើញលើ links/buttons។
- [ ] Animation មិនចាំបាច់សម្រាប់យល់មាតិកា។
- [ ] Filter controls មាន label និងអាចប្រើ keyboard។
- [ ] Grid មិនធ្វើឱ្យមាន overflow។
- [ ] Style ដដែលៗត្រូវបានកំណត់ជាមួយ component class/tokens។