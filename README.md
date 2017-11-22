<p align="center">
<img src="https://pigjian.com/images/v-distpicker.png" alt="Powered By Jiajian Chan" width="160">
</p>

<p align="center">A flexible, highly available district selector for picking provinces, cities and districts of China.</p>

<p align="center">
  <br>
  <b>创造不息，交付不止</b>
  <br>
  <a href="https://www.yousails.com">
    <img src="https://yousails.com/banners/brand.png" width=350>
  </a>
</p>

# V - Distpicker

Here is [documents](http://distpicker.iline.co/)

## Installation

```javascript
npm install v-distpicker --save
```

Or

```javascript
yarn add v-distpicker --save
```

## Usage

**Register component**

Registe global component:

```javascript
import Distpicker from 'v-distpicker'

Vue.component('v-distpicker', Distpicker)
```

Registe component:

```javascript
import VDistpicker from 'v-distpicker'

export default {
  components: { VDistpicker }
}
```

**How to use**

Basic:

```javascript
<v-distpicker></v-distpicker>
```

Default Value:

```javascript
<v-distpicker province="广东省" city="广州市" area="海珠区"></v-distpicker>
```

Mobile:

```javascript
<v-distpicker type="mobile"></v-distpicker>
```

QuickPassCity:

```html
<!-- 如果是直辖市，则快速跳过市的选择，直接进入区的选择 -->
<v-distpicker quick-pass-city></v-distpicker>
```

Sort Province, City, Area:

```html
<v-distpicker :sort-province="provinceSort" :sort-city="citySort" :sort-area="areaSort"></v-distpicker>
```
```javascript
export default {
  methods: {
    provinceSort(provinceX, provinceY) { 
      //shoul return 1, 0 or -1
    },
    citySort(province, cityX, cityY) { 
      //shoul return 1, 0 or -1
    },
    areaSort(province, city, areaX, areaY) { 
      //shoul return 1, 0 or -1
    },
  },
}
```

## Contributors

- [Jiajian Chan](http://github.com/jcc)

## Thanks

- [Distpicker](https://github.com/fengyuanchen/distpicker)

## License

The plugin is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT).
