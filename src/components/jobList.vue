<script setup lang="ts">

  import { defineProps, PropType } from 'vue';
  import Job from '../types/job'
  
  defineProps<{jobs: {
    type: Job[],
    required: true
  }; order: {
    type: String,
    required: true
  }}>()

</script>

<template>
 <div class="job-list">
  <p>
    ordre par {{ order }}
  </p>
  <ul>
    <li v-for="job in jobs" :key="job.id" style="list-style: none;">
      <span>{{ job.title }} - {{ job.salary }}</span>
    </li>
  </ul>
 </div>
</template>

<style lang="scss" scoped>
  
</style>