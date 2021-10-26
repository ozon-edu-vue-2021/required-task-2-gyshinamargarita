<template>
  <div class="item" v-on:click='setActive' v-bind:class="{link:object.type ==='link', file:object.type ==='file', active:active}">
    {{object.name}}
  </div>
</template>

<script>

export default {
  name: 'Item',
  props: {
    object: Object
  },
  data:()=>({active:false}),
  methods:{
      setActive:function(){
        this.active =!this.active
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.link{
    color:blue;
    border-bottom: 1px solid blue;
}
.file{
    color:salmon
}
.file.active{
    color:slateblue
}
.link.active{
    color:pink;
    border-bottom:1px solid pink;
}
</style>