<template>
   <div class="jobs-list">
      <ul>
         <li 
            v-for="job in jobs"
            :key="job.id"
         >
            <h2> {{job.title}} {{job.location}}</h2>
            <div class="salary">
               <p>{{job.salary}} rupees</p>
            </div>
            <div class="description">
               <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Temporibus eum eius, nam saepe blanditiis aliquid ab nisi voluptate. Perspiciatis quis porro ad facere minima, obcaecati odit distinctio voluptate quaerat est?</p>
            </div>
         </li>
      </ul>
   </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'
import Job from '../types/Job'

export default defineComponent({
   props:{
      jobs:{
         type: Array as PropType<Job[]>,
         required: true 
      }
   },
   setup() {
      
   }
})
</script>

<style scoped>
   
</style>