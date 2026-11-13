# មេរៀន ៦៖ CSS Units

## គោលបំណង
ជ្រើស unit សមស្រប ដើម្បីឱ្យ layout អាចបត់បែនជាមួយ font និង viewport។

## Absolute និង relative
- **px**៖ CSS pixel; មើលទៅថេរនៅ layout scale ប៉ុន្តែមិនមានន័យថា pixel រូបវន្តលើអេក្រង់ជានិច្ចទេ។
- **%**៖ គិតធៀប parent ឬ containing block; reference អាស្រ័យ property។
- **em**៖ សម្រាប់ font-size គិតតាម font-size របស់ parent; សម្រាប់ properties ផ្សេងៗគិតតាម font-size របស់ element នោះ។
- **rem**៖ គិតតាម root element font-size; សមស្របសម្រាប់ sizing ដែលមាន scale រួម។
- **vw/vh**៖ 1% នៃ viewport width/height; 100vh អាចមានបញ្ហាជាមួយ browser UI លើ mobile ក្នុង context ខ្លះ។
- **vmin/vmax**៖ 1% នៃ viewport dimension តូចបំផុត/ធំបំផុត។
- **ch**៖ ប្រហែលទទឹង glyph “0” របស់ font បច្ចុប្បន្ន; មានប្រយោជន៍សម្រាប់ទទឹងអត្ថបទ។
- **fr**៖ ចំណែកទំនេរក្នុង CSS Grid; ប្រើតែក្នុង grid track sizing។

## ឧទាហរណ៍
~~~css
html { font-size: 100%; }
.card {
  width: min(100%, 40rem);
  padding: 1.5rem;
  margin-inline: auto;
}
.title { font-size: clamp(1.5rem, 4vw, 3rem); }
.copy { max-width: 65ch; }
.grid { display: grid; grid-template-columns: 1fr 2fr; }
~~~
កំណត់ width: 100% អាចពេញ parent; rem ធ្វើឱ្យ spacing ស្រប; clamp កំណត់ min, preferred, max។ កុំកំណត់ font-size របស់ root ទាបដើម្បីបង្ខំអ្នកប្រើ; គោរព browser settings។

## ជ្រើស unit
- ប្រើ rem សម្រាប់ typography/spacing ដែលគួរគោរព browser zoom និង font preference។
- ប្រើ % សម្រាប់ទំហំធៀប container។
- ប្រើ fr សម្រាប់ចែក columns ក្នុង Grid។
- ប្រើ px សម្រាប់ border ស្តើង ឬតម្លៃតូចដែលត្រូវការគ្រប់គ្រងច្បាស់។
- ប្រើ viewport units ជាមួយ min/max ឬ clamp ដើម្បីកុំឱ្យចំណងជើងលើស/តូចពេក។

## អនុវត្ត
ធ្វើ card មាន max-width 40rem ប៉ុន្តែទទឹងមិនលើស parent, padding 1.5rem និងចំណងជើង fluid ដោយ clamp។ ពិនិត្យ zoom 200% និង viewport តូច។

## សំណួរ
1. rem គិតធៀបអ្វី?
2. តើ fr ប្រើក្នុងបរិបទណា?
3. ហេតុអ្វី 4vw តែមួយមិនល្អសម្រាប់ font-size?

**ចម្លើយ**៖ rem គិតធៀប root font-size; fr ជា Grid track unit; viewport តូចធ្វើឱ្យអក្សរតូចខ្លាំង ហើយ viewport ធំធ្វើឱ្យធំពេក—ដាក់ clamp។