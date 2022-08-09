<template>
  <Options @scaleChange="onScaleChange" />
  <Table />
</template>

<script>
import Table from './components/Table.vue'
import Options from './components/Options.vue'

export default {
  name: 'App',
  components: {
    Table,
    Options
  },
  methods: {
    onScaleChange(name, value) {
      console.log(name + ", " + value);
    }
  }
}
</script>

<style>
#app {
  font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
