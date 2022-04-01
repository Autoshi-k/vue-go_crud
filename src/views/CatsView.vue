<script>
import cats from '@/data/Cats';
// console.log(cats)
export default {
  data() {
    return { 
      cats,
      th: []
    }
  },
  computed: {
    getTh() {
      const thArray = [];
      if (cats) for (let props in cats[0]) { thArray.push(props) }
      th = thArray;
    }
  },
  mounted: function() {
    console.log('mounted', cats)
  },
  updated: function() {
    console.log('updated this', this.cats)
  }

}
</script>


<template>
  <div class="cats-view">
    <h1>CATSSS</h1>
    <table>
      <tr>
        <th v-for="(item, index) in Object.keys(this.cats[0])" :key="index">{{item}}</th>
      </tr>
      <tr v-for="(cat, index) in this.cats" :key="index">
        <td v-for="(item, index) in cat" :key="index">{{item}}</td>
      </tr>
    </table>
  </div>
</template>

<style>

</style>
