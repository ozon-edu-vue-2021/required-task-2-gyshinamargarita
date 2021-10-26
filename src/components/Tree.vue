<template>
  <div class="tree">
      <Folder :object="node_modules"/>
  </div>
</template>

<script>
import node_modules from '../../public/static/node_modules.json'
import Folder from './Folder.vue'
export default {
  name: 'Tree',
  data:()=>({node_modules}),
  components:{ Folder }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
