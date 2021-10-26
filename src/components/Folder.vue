<template>
  <div class="folder">
    <div v-if="object.type==='directory'">
        <button class="folder-button" v-on:click='toggleShowChildren'>{{object.name}}</button>
        <div  class="folder-list" v-if='show'>
            <div class="folder-list-element" v-for="element in object.contents" v-bind:key="element.name">
                <Folder :object="element"/>
            </div>
        </div>
    </div>
    <div v-else>
        <Item :object="object"/>
    </div>
  </div>
</template>

<script>
import Item from './Item.vue'
export default {
  name: 'Folder',
  props: {
    object: Object
  },
  data:()=>({ show:false }),
  components:{Item},
  methods:{
      toggleShowChildren:function(){ 
          this.show = !this.show
          return this 
          }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.folder{
    display: flex;
}
.folder-button{
    background: none;
    outline: none;
    font-size: 17px;
    border-radius: 10px;
    border: 1px solid grey;
    color:grey;
}
.folder-list{
    margin-left: 30px;
   
}
.folder-list > *{
    margin-top: 10px;
    }
</style>
