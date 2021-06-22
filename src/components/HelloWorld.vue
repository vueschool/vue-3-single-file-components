<template>
  <div class="hello">
    <h1 class="username">{{msg}}</h1>
    <button @click="showUsername = !showUsername">Toggle Username</button>
    <div v-if="showUsername">
      <BigYellowUsername username="danielkellyio" />
    </div>
  </div>
</template>

<script>
import { defineAsyncComponent } from 'vue'
export default {
  name: 'HelloWorld',
  components: {
    BigYellowUsername: () => defineAsyncComponent(import(/* webpackChunkName: "BigYellowUsername" */ './BigYellowUsername.vue'))
  },
  props: {
    msg: String
  },
  data () {
    return {
      showUsername: false
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
