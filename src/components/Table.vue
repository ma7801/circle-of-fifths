<template>
  <table>
    <thead>
      <tr>
        <th v-for="(title, key) in cofData[0]" :key="title" v-show="showColumns[key]">{{ title }}</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(row, index) in cofData" :key="row.majorKey"> 
        <td v-for="(col, key) in row" :key="col" v-show="index !== 0 && showColumns[key]" >
            {{col}}
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
import jsonData from './Data.json';

export default {
  data () {
    return {
        cofData: {},
        showColumns: {
          "chromaticOrder": false,
          "keyMajor": true,
          "numBlackKeys": false,
          "fingeringMajorLH": true,
          "fingeringMajorRH": true,
          "sharps": false,
          "flats": false,
          "keyNaturalMinor": false,
          "fingeringMinorLH": false,
          "fingeringMinorRH": false
        }
    }
  },
  methods: {

  },
  mounted() {
    this.cofData = jsonData;
  }

}
</script>

<style>
table {
  border-collapse: collapse;
  margin: 20px auto;

}
td, th {
  border: 1px #ddd solid;
  padding: 10px;
  text-align: center;
}

</style>