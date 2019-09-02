<template>
  <div class="hello">
    <h1></h1>
    <span>{{index}}、</span>

    <button v-on:click="add">+</button>

    <span>{{number}}</span>
    <button v-on:click="desc">-</button>
    
  </div>
</template>

<script>
export default {
  data(){
      return{
      number:this.index
      };
  },
  props: {
    index:Number
  },
  created(){
      this.$emit('update',this.number);
  },
  destroyed(){
      this.$emit('update',-this.number);
  },
  methods: {
      desc(){
          this.number--;
          this.$emit('update',-1);

      },
      add(){
        this.$emit('update',1);
        this.number++;
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
