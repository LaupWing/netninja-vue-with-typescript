<template>
   <div class="app">
      <p>{{ name }}</p>
      <button @click="changeName('zelda')">Change Name</button>
      <JobList :jobs="jobs"/>
   </div>
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs, ref } from "vue";
import Job from "./types/Job";
import JobList from './components/JobList.vue'

export default defineComponent({
   name: "App",
   components: {
      JobList
   },
   setup() {
      const state = reactive({
         name: "Link",
         age: 25 as string | number,
      });

      const jobs = ref<Job[]>([
         {
            title: "farm worker",
            location: "lon lon ranch",
            salary: 30000,
            id: "1",
         },
         {
            title: "quarryman",
            location: "death mountain",
            salary: 40000,
            id: "2",
         },
         {
            title: "flute player",
            location: "the lost woods",
            salary: 35000,
            id: "3",
         },
         { title: "fisherman", location: "lake hylia", salary: 21000, id: "4" },
         {
            title: "prison guard",
            location: "gerudo valley",
            salary: 32000,
            id: "5",
         },
      ]);
      return {
         ...toRefs(state),
         jobs
      };
   },
   data() {
      return {
         name: "Link",
      };
   },
   methods: {
      changeName(name: string) {
         this.name = name;
      },
   },
});
</script>

<style>
</style>
