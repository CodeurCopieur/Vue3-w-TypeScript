<script setup lang="ts">
import { ref } from 'vue';
import TypeScript from './components/TypeScript.vue';
import JobList from './components/jobList.vue';
import Job from './types/job'
import orderTerm from './types/orderTerm'

const order = ref<orderTerm>('salary')
const jobs = ref<Job[]>([
  {title: 'Dev js', location: 'paris',  salary: 45000, id: 'SG23'},
  {title: 'Dev ts', location: 'lyon',  salary: 50000, id: 'SG24'},
  {title: 'Dev py', location: 'marseille',  salary: 55000, id: 'SG25'}]);

  
  const handleClick = (term: orderTerm) => {
    order.value = term
  };

</script>

<template>
  <TypeScript msg="Type Script" />
  <header>
    <div class="order">
      <button @click="handleClick('title')">Ordre par title</button>
      <button @click="handleClick('location')">Ordre par localisation</button>
      <button @click="handleClick('salary')">Ordre par salaire</button>
    </div>
  </header>
  <JobList :jobs="jobs" :order="order" />
  <!-- <ul>
    <li v-for="job in jobs" :key="job.id" style="list-style: none;">
      <span>{{ job.title }} - {{ job.salary }}</span>
    </li>
  </ul> -->
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
