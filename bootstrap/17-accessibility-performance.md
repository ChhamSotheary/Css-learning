# Chapter 17៖ Accessibility, Performance និង Testing

## Accessibility មិនមកដោយស្វ័យប្រវត្តិ
Bootstrap class បង្កើតរូបរាង/behavior; semantic HTML និងការប្រើប្រាស់ត្រឹមត្រូវនៅតែជាការទទួលខុសត្រូវរបស់អ្នកអភិវឌ្ឍន៍។ Component ដែលមើលស្អាតអាចមិន accessible បើគ្មាន label, keyboard, focus, contrast ឬ state។

## Checklist
- ប្រើ landmark និង heading hierarchy ត្រឹមត្រូវ។
- Form fields មាន label, help/error text និង aria-describedby តាមសមស្រប។
- Buttons/links មានឈ្មោះអាចយល់; icon-only button ត្រូវមាន accessible name។
- Focus indicator មើលឃើញ និង tab order មានហេតុផល។
- State ដូច expanded/selected/pressed ត្រូវ update ARIA តាម behavior។
- Contrast អត្ថបទ/ផ្ទៃត្រូវគ្រប់គ្រាន់; កុំប្រើពណ៌តែមួយបង្ហាញ status។
- Modal/offcanvas/dropdown/tab ត្រូវសាក keyboard, Escape និង focus behavior។
- Khmer font/line-height/wrapping ត្រូវសាកលើ device ពិត។

## Performance
- Import CSS/JS តែដែលត្រូវការ បើ build tooling អនុញ្ញាត។
- ប្រើ minified production build, cache និង HTTPS។
- បង្រួម/ប្តូររូបភាពទៅ format សមស្រប និងកំណត់ width/height។
- កុំប្រើ components/animations ច្រើនដោយមិនចាំបាច់។
- Sass customization អាចបញ្ចូលតែ components ដែលប្រើ ប៉ុន្តែត្រូវរក្សា dependency order។
- វាស់ performance ជាមួយ browser tools; កុំ optimize ដោយស្មាន។

## Testing workflow
1. DevTools console: រក JS error និង missing asset។
2. Responsive: សាក width តូច/ធំ និង breakpoint edges។
3. Keyboard only: Tab, Shift+Tab, Enter, Space, Escape, arrows តាម component។
4. Zoom/reflow: 200% និងទទឹងតូចប្រហែល 320 CSS px។
5. Screen reader: សាក name/role/value/state នៅ components interactive។
6. Theme: light/dark, high contrast, reduced motion។
7. Browser: Chrome/Firefox/Safari/Edge តាម audience និង support policy។
8. Network/performance: CSS/JS bytes, image load, cache, slow connection។

## អនុវត្ត
យក form និង modal មកធ្វើ keyboard/accessibility audit។ សរសេរ issue log: អ្វីខូច, ជំហានបង្កើតឡើងវិញ, ជួសជុល និងរបៀបផ្ទៀងផ្ទាត់។

## សំណួរ
1. តើ class btn ធានាថា button accessible ដែរឬទេ?
2. តើត្រូវសាកតែ desktop Chrome គ្រប់គ្រាន់ទេ?
3. តើ performance optimization ត្រូវផ្អែកលើអ្វី?

**ចម្លើយ**៖ មិនធានា; ត្រូវសាក keyboard/screen reader/responsive និង browsers តាម support policy; វាស់ដោយ tools និងផ្អែកលើ bottlenecks ពិត។