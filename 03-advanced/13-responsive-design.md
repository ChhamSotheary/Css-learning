# មេរៀន ១៣៖ Responsive Web Design

## គោលបំណង
រៀបចំទំព័រដែលដំណើរការបានល្អលើទូរស័ព្ទ, tablet និង desktop ដោយចាប់ពី mobile first។

## Viewport meta
~~~html
<meta name="viewport" content="width=device-width, initial-scale=1">
~~~
គ្មាន meta នេះទេ browser mobile អាច render ទំព័រដូច viewport ធំ ហើយបង្រួមវាទៅតូច។ បន្ថែមវាក្នុង head។

## Mobile-first និង media query
~~~css
.layout { display: grid; grid-template-columns: 1fr; gap: 1rem; }
@media (min-width: 48rem) {
  .layout { grid-template-columns: 15rem 1fr; }
}
~~~
Mobile-first សរសេរ style មូលដ្ឋានសម្រាប់ទទឹងតូច រួចបន្ថែមលក្ខខណ្ឌសម្រាប់ទំហំធំ។ Breakpoint គួរតាមពេល content មិនសម មិនមែនតាមឈ្មោះឧបករណ៍ជាក់លាក់ទេ។ Desktop-first អាចប្រើ max-width; កុំលាយដោយគ្មានគោលការណ៍។

## Fluid sizing និងរូបភាព
~~~css
img { display: block; max-width: 100%; height: auto; }
h1 { font-size: clamp(1.8rem, 5vw, 3.5rem); }
.container { width: min(100% - 2rem, 72rem); margin-inline: auto; }
~~~
Responsive image មិនលើស container; width/height attribute ក្នុង HTML ក៏ជួយ browser រៀបកន្លែងមុនរូប load។ ប្រើ picture/srcset ក្នុង HTML សម្រាប់ប្រភពរូបខុសគ្នាតាម resolution/art direction។

## Navigation, Flexbox និង Grid
បើ links មិនសមនៅទទឹងតូច អាច wrap, ប្តូរ layout ឬប្រើ menu button ដោយ HTML/JavaScript ដែល accessible; កុំលាក់ navigation ទាំងស្រុងដោយគ្មានវិធីបើក។ Flexbox/Grid ជួយឱ្យ items បត់បែន; auto-fit/minmax អាចកាត់បន្ថយ media queries។

## Responsive testing
សាក DevTools device mode និងទំហំជាច្រើន; មើល horizontal scroll, text zoom, focus, image crop, long Khmer/English text និង form controls។ កុំសន្មតថា mobile គ្រាន់តែ desktop តូច។

## លំហាត់
ធ្វើ landing page មាន hero និង 3 cards។ Mobile: មួយ column; tablet: ពីរ; desktop: បី។ កំណត់ container max-width និងរូបភាព fluid។ សាក zoom 200% និង keyboard navigation។

## សំណួរ
1. Mobile-first មានន័យដូចម្តេច?
2. តើ breakpoint ជ្រើសដោយរបៀបណា?
3. ហេតុអ្វីរូបភាពត្រូវ max-width:100%?

**ចម្លើយ**៖ ចាប់ពី style សម្រាប់ viewport តូច; ជ្រើសពេល content ត្រូវការផ្លាស់ layout; ដើម្បីមិនឱ្យរូបលើស parent។