<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <input type="text" name="text" v-model="text">
    <br>
    <button @click='post'>Click me</button>
  </div>
</template>

<script>
import Methods from '@/api/methods'

export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      text: ''
    }
  },
  methods: {
    async post() {
      let element = { text: this.text }
      let response = await Methods.testPosting(element)
      console.log(response)
    }
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
