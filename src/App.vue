<template>
  <div id="app">
    <input v-model="num"/>

    <counter v-for="n in parseInt(num)" v-bind:key="n" v-bind:counter = "n" v-bind:index = "n" v-on:update="sum += $event"/>
    sum:{{sum}}
  </div>
</template>

<script>
import counter from './components/counter.vue'
export default {
  name: 'app',
  components: {
    counter
  },
  data(){
    return{
      num:0,
      sum:0
    }
  },
  methods:{
    
  }

  
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
