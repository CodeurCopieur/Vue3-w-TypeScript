<script setup lang="ts">

  import { defineProps } from 'vue';
  import Job from '../types/job'
  
  defineProps<{jobs: Job[]}>()

</script>

<template>
 <div class="job-list">
  <ul>
    <li v-for="job in jobs" :key="job.id" style="list-style: none;">
      <span>{{ job.title }} - {{ job.salary }}</span>
    </li>
  </ul>
 </div>
</template>

<style lang="scss" scoped>
  
</style>