# Chapter 14៖ Bootstrap ជាមួយ npm, Vite និង Sass

## គោលបំណង
យល់ភាពខុសគ្នារវាង CDN និង package workflow ហើយបង្កើត build ដែលអាចកែ Bootstrap Sass បាន។

## CDN ឬ npm?
- **CDN**៖ ស្រួលសម្រាប់ demo/static page; browser ទាញ CSS/JS ពី internet; version ត្រូវ pin ហើយ production ត្រូវប្រើ SRI។
- **npm**៖ Bootstrap ជា dependency ក្នុង project; អាច import components ដែលត្រូវការ, compile Sass, bundle និង version-lock។
- **Vite**៖ dev server និង build tool; វាមិនមែនជា Bootstrap ទេ—វាបម្រើជា build pipeline សម្រាប់ project។

## Project setup (គំរូ)
~~~bash
npm init -y
npm install bootstrap
npm install --save-dev vite sass
~~~
បន្ថែម scripts ក្នុង package.json តាម version Vite៖
~~~json
{
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview"
  }
}
~~~
បង្កើត index.html និង src/main.js៖
~~~js
import 'bootstrap/dist/css/bootstrap.min.css';
import 'bootstrap/dist/js/bootstrap.bundle.min.js';
import './styles.scss';
~~~
Bootstrap bundle រួម Popper សម្រាប់ dropdown/popover/tooltip។ បើ import JS ទាំងមូល ទទួល components ទាំងអស់; project ធំអាច import modules តែដែលត្រូវការ និងពិនិត្យ dependency/config របស់ bundler។

## Sass customization
បង្កើត src/styles.scss ហើយកំណត់ overrides មុន import Sass៖
~~~scss
$primary: #075985;
$border-radius: 0.75rem;
$spacer: 1rem;

@import "bootstrap/scss/bootstrap";
~~~
Bootstrap Sass មានលំដាប់ import dependencies។ សម្រាប់ការកំណត់ theme colors/custom utilities សូមធ្វើតាម Sass customization guide របស់ version 5.3; កុំចម្លង import order ចាស់ពី v4 ឬ blog។ សម្រាប់ Sass deprecations សូមពិនិត្យ workflow ដែល Bootstrap version នោះគាំទ្រ។

## Production workflow
1. ចាក់សោ version ក្នុង package-lock.json និង commit lockfile។
2. រត់ dev server សម្រាប់ការអភិវឌ្ឍ។
3. រត់ build និង preview production bundle។
4. ពិនិត្យទំហំ CSS/JS និងកុំ import components មិនប្រើនៅពេល optimize។
5. កុំដាក់ secret ក្នុង frontend bundle; CSS/JS ទាំងអស់អាចមើលបានពី browser។

## អនុវត្ត
បង្កើត Vite project ដែលបង្ហាញ Bootstrap button និង responsive grid។ ប្ដូរ primary color តាម Sass, run build, បើក preview និងពិនិត្យថា output CSS មាន theme ថ្មី។

## សំណួរ
1. CDN និង npm ខុសគ្នាដូចម្តេច?
2. Vite តួនាទីអ្វី?
3. ហេតុអ្វីត្រូវ lock dependency version?

**ចម្លើយ**៖ CDN load file remote; npm រក្សា dependency ក្នុង project និង build; Vite បម្រើ dev/build; lockfile ធ្វើឱ្យ install ស្របគ្នា។