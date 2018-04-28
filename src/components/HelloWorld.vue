<template>
  <div>
    <CTHours></CTHours>
    <div class="container" style="marginTop: 30px">
      <CTSevenDays></CTSevenDays>
      <CTLiving></CTLiving>
    </div>
  </div>
</template>

<script>
import CTHours from './CTHours'
import CTSevenDays from './CTSevenDays'
import CTLiving from './CTLiving'

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  components: {
    CTHours,
    CTSevenDays,
    CTLiving
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
