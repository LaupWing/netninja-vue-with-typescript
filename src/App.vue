<template>
   <div class="app">
      <p>{{name}}</p>
      <button @click="changeName('zelda')">Change Name</button>
   </div>
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs } from "vue";

export default defineComponent({
   name: "App",
   components: {
   },
   setup(){
      const state = reactive({
         name: 'Link',
         age: 25 as string | number
      })
      return {
         ...toRefs(state)
      }
   },
   data(){
      return{
         name: 'Link'
      }
   },
   methods:{
      changeName(name: string){
         this.name = name
      }
   }
});
</script>

<style>

</style>
