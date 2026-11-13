# Project 3៖ Admin Dashboard Capstone

**កម្រិត៖ Advanced | Chapters 09–18**

## គោលដៅ
បង្កើត dashboard មាន responsive navbar/sidebar, KPI cards, data table, form, modal, toast និង theme switcher។

## Requirements
- ប្រើ Bootstrap grid/utilities សម្រាប់ responsive layout។
- Component classes និង custom CSS មាន architecture ច្បាស់; បើ project ធំប្រើ npm/Vite/Sass។
- Form មាន label, validation messaging និង server-validation note។
- Table មាន caption, scope headers និង responsive wrapper។
- Modal មាន title, close control និង keyboard/focus behavior។
- Toast សម្រាប់ status ដែលសមស្រប; កុំ auto-hide error សំខាន់។
- Light/dark theme ប្រើ data-bs-theme និង custom tokens។
- UI គាំទ្រ Khmer text, keyboard, zoom និង reduced-motion preference។
- JS behavior មិនទុកចិត្ត frontend ជា security/authorization boundary។

## ជំហាន
1. បង្កើត source project និងកំណត់ Bootstrap version។
2. រៀប navigation, main content និង sidebar តាម mobile-first។
3. បង្កើត KPI cards និង responsive data table។
4. បង្កើត form validation UI; កុំភ្លេច server-side validation។
5. បន្ថែម modal/toast ដោយ data API ឬ class API។
6. បន្ថែម theme switcher និង test light/dark contrast។
7. ធ្វើ accessibility/performance audit និងសរសេរ run instructions។

## Checklist
- [ ] Layout ដំណើរការលើ mobile និង desktop។
- [ ] Keyboard អាចចូល controls ទាំងអស់ និង focus មិនបាត់។
- [ ] Modal/offcanvas បើកបិទបាន និង state accessible។
- [ ] Dark mode មិនបាត់ contrast ឬ focus ring។
- [ ] Table អាចពិនិត្យលើទទឹងតូច។
- [ ] Production build import CSS/JS តាមតម្រូវការ។
- [ ] README ពន្យល់ version, setup និង tradeoffs។