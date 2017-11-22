<template>
  <div class="row">
    <div class="example">
      <h5>Sort</h5>
      <div class="example-box">
        <div class="box-left d-flex align-items-baseline">
          <div class="col-md-7">
            <v-distpicker :sort-province="provinceSort" :sort-city="cityWithinHeBeiSort" :sort-area="shanghaiAreaSort" @province="selectProvince" @city="selectCity" @area="selectArea"></v-distpicker>
          </div>
          <div class="content-show col-md-5">
            <pre><code>{{ select }}</code></pre>
          </div>
        </div>
        <div class="box-right col-md-12" v-if="showCode">
<pre class=" language-javascript code-toolbar"><code class=" language-javascript"><span class="token operator">&lt;</span>template<span class="token operator">&gt;</span>
  <span class="token operator">&lt;</span>v<span class="token operator">-</span>distpicker<span class="token operator">&gt;</span><span class="token operator">&lt;</span><span class="token operator">/</span>v<span class="token operator">-</span>distpicker<span class="token operator">&gt;</span>
<span class="token operator">&lt;</span>template<span class="token operator">&gt;</span>

<span class="token operator">&lt;</span>script<span class="token operator">&gt;</span>
<span class="token keyword">import</span> VDistpicker <span class="token keyword">from</span> <span class="token string">'v-distpicker'</span>

<span class="token keyword">export</span> <span class="token keyword">default</span> <span class="token punctuation">{</span>
  components<span class="token punctuation">:</span> <span class="token punctuation">{</span> VDistpicker <span class="token punctuation">}</span><span class="token punctuation">,</span>
<span class="token punctuation">}</span>
<span class="token operator">&lt;</span><span class="token operator">/</span>script<span class="token operator">&gt;</span></code></pre>
        </div>
        <div class="box-footer" @click="showCode = !showCode">
          {{ showCode ? 'Hide Code' : 'Show Code' }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import VDistpicker from '../../../src/Distpicker'

export default {
  components: { VDistpicker },
  data() {
    return {
      showCode: false,
      select: { province: '', city: '', area: '' },
    }
  },
  methods: {
    selectProvince(value) {
      this.select.province = value
      console.log(value);
    },
    selectCity(value) {
      this.select.city = value
      console.log(value);
    },
    selectArea(value) {
      this.select.area = value
      console.log(value);
    },
    shanghaiAreaSort(province, city, areaX, areaY) {
        // 排上海市的区
        if(province === '上海市') {
            const areas = {
            '闵行区': 1,
            '静安区': 2,
            '浦东新区': 3,
            }
            const indexX = areas[areaX] || 4
            const indexY = areas[areaY] || 4
            return indexX > indexY ? 1 : indexX < indexY ? -1 : 0 
        }
    },
    provinceSort(provinceX, provinceY) {
        const provinces = {
        '上海市': 1,
        '江苏省': 2,
        '浙江省': 3,
        }
        const indexX = provinces[provinceX] || 4
        const indexY = provinces[provinceY] || 4
        return indexX > indexY ? 1 : indexX < indexY ? -1 : 0 
    },
    cityWithinHeBeiSort(province, cityX, cityY) {
        // 排河北省内的市
        if(province === '河北省') {
            const cities = {
            '石家庄市': 1,
            '张家口市': 2,
            '沧州市': 3,
            }
            const indexX = cities[cityX] || 4
            const indexY = cities[cityY] || 4
            return indexX > indexY ? 1 : indexX < indexY ? -1 : 0 
        }
    },
  },
}
</script>
