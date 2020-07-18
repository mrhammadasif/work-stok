<template>
  <td class="me">{{something.toUpperCase()}}</td>
</template>
<script>
const chance = require('chance')()
export default {
  props: ['value'],
  computed: {
    something () {
      return chance.letter()
    }
  }
}
</script>
<style lang="scss" scoped>
.me {
  width: 40px;
  height: 40px;
  font-weight: bold;
  font-size: 20px;
}
</style>
