# មេរៀន ៧៖ CSS Box Model

## គោលបំណង
យល់ថា element មួយកាន់កាប់ទំហំដោយ content, padding, border និង margin ហើយគណនាទំហំបានត្រឹមត្រូវ។

~~~text
ខាងក្រៅ: margin
┌──────────────────────────┐
│ border                   │
│  ┌────────────────────┐  │
│  │ padding            │  │
│  │  ┌──────────────┐  │  │
│  │  │ content      │  │  │
│  │  └──────────────┘  │  │
│  └────────────────────┘  │
└──────────────────────────┘
~~~
- **Content**៖ អត្ថបទ/រូបភាព និងទំហំ width/height មូលដ្ឋាន។
- **Padding**៖ ចន្លោះក្នុង border ជុំវិញ content។
- **Border**៖ ស៊ុមក្រៅ padding។
- **Margin**៖ ចន្លោះខាងក្រៅ element ដែលបំបែកពីអ្នកជិតខាង។

## box-sizing
តាម default **content-box**: width គ្រាន់តែ content។ ដូច្នេះទទឹងពិត = width + padding ឆ្វេងស្តាំ + border ឆ្វេងស្តាំ។
~~~css
*,
*::before,
*::after { box-sizing: border-box; }
.card {
  width: 20rem;
  padding: 1rem;
  border: 2px solid #ccc;
}
~~~
ជាមួយ **border-box**, width រួម content+padding+border; ងាយគ្រប់គ្រង។ វាមិនរួម margin ទេ។

## Constraints និង overflow
~~~css
.panel {
  width: 100%;
  max-width: 60rem;
  min-height: 10rem;
  overflow: auto;
}
~~~
**min-width/max-width**, **min-height/max-height** កំណត់ដែន។ overflow មាន visible, hidden, auto, scroll; hidden អាចកាត់ content ឬ focus ring ដូច្នេះប្រើដោយប្រុងប្រយ័ត្ន។

## Margin collapsing
ក្នុង normal block flow បញ្ឈរ margin ពីរដែលជាប់គ្នាអាច collapse ទៅជាតម្លៃធំជាង មិនមែនបូកគ្នាទេ។ Flex/Grid items មិន collapse ដូច block flow ទេ។ ប្រើ padding, gap ឬ layout container ដើម្បីគ្រប់គ្រង spacing ឱ្យច្បាស់។

## អនុវត្ត
បង្កើត card width 320px, padding 20px, border 2px និង margin auto។ សាក content-box vs border-box នៅ DevTools។ បន្ថែម max-width: 100% ដើម្បីកុំឱ្យលើស mobile។

## លំហាត់
1. border-box រួមអ្វីខ្លះក្នុង width?
2. តើ margin ចូលក្នុង width ដែរឬទេ?
3. តើ overflow:auto ជួយអ្វី?

**ចម្លើយ**៖ រួម content, padding, border; margin មិនរួម; auto បង្ហាញ scroll តែពេល content លើស។