<template>
  <div id="app">
    <p class="text-center">{{key}} - {{rows}} - {{cols}}</p>
    <div class="p-4 g-4 d-flex align-items-center">
      <label class="p-0 m-0" for="">Rows</label>
      <input v-model.number="rows" :min="2" :max="20" type="range" class="form-control ml-2 mr-4 m-0">
      <label class="p-0 m-0" for="">Columns</label>
      <input v-model.number="cols" min="2" step="1" max="20" type="range" class="form-control ml-2 m-0">
      <button class="btn btn-primary ml-4" @click="regenKey">Regenerate!</button>
    </div>
    <table class="table-bordered" :key="key">
      <tr v-for="row in rows" :key="key + row">
        <cell v-for="col in cols" :value="key" :key="key + row + col" />
      </tr>
    </table>
  </div>
</template>

<script>
import 'bootstrap/dist/css/bootstrap.css'
import Cell from './components/Cell.vue'
const chance = require('chance')()
export default {
  name: 'App',
  data () {
    return {
      key: '1231232c',
      rows: 4,
      cols: 4
    }
  },
  methods: {
    regenKey () {
      this.key = chance.guid()
    }
  },
  components: {
    Cell
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
