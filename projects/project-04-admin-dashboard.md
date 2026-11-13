# Project 4៖ Admin Dashboard

**កម្រិត៖ Expert**  
**មេរៀនពាក់ព័ន្ធ៖** 11–13 និង 19–22

## គោលបំណង
បង្កើត dashboard responsive មាន navigation, summary cards, data table/list, form control និង light/dark theme។

## តម្រូវការ
- Layout ធំប្រើ CSS Grid areas; card internals/toolbar ប្រើ Flexbox។
- Design tokens សម្រាប់ color, spacing, typography, radius និង shadow។
- ប្រើ logical properties សម្រាប់ padding/margin ដែលសម writing direction។
- Container query សម្រាប់ component ដែលប្រើក្នុង container ខុសៗគ្នា; មាន base style fallback។
- CSS architecture ចែកជា tokens, base, layout, components។
- Dark theme កែ tokens ទាំងមូល និងរក្សា contrast/focus។
- Sidebar/navigation បត់ទៅ mobile ដោយមាន behavior accessible; CSS មិនធ្វើឱ្យ content ចាំបាច់បាត់។
- Table/data អាច scroll ដោយមាន context; កុំលាក់ column សំខាន់ដោយគ្មានជម្រើស។

## ជំហាន
1. រៀបចំ wireframe និង semantic HTML។
2. បង្កើត tokens និង layers (ឬកំណត់ cascade order ដោយច្បាស់)។
3. បង្កើត grid areas សម្រាប់ header/sidebar/main។
4. បង្កើត reusable cards/buttons/forms/table styles។
5. បន្ថែម responsive behavior និង dark theme។
6. សាក keyboard, zoom 200%, mobile, reduced motion និង Khmer content។
7. បន្ថែម README ពន្យល់ architecture, browser support និង tradeoffs។

## Checklist
- [ ] Dashboard មាន heading hierarchy និង landmark ត្រឹមត្រូវ។
- [ ] Theme ទាំងពីរមាន contrast និង focus state ច្បាស់។
- [ ] UI ប្រើបានដោយ keyboard។
- [ ] Data/table អាចអាននៅ viewport តូច។
- [ ] CSS អាចរក token/component បានងាយ។
- [ ] Container query មាន fallback ដែលសម។
- [ ] មិនប្រើ important override ដោយគ្មានហេតុផល។