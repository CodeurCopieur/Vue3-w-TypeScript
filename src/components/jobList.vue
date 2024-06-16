<script setup lang="ts">

  import { defineProps, computed, PropType } from 'vue';
  import Job from '../types/job'
  import orderTerm from '../types/orderTerm'
  
  const props = defineProps({
    jobs: {
    type: Array as PropType<Job[]>,
    required: true
  }, 
  order: {
    type: String as PropType<orderTerm>,
    required: true
  }
});


  const orderedJobs = computed(() => {
    return [...props.jobs].sort((a: Job, b: Job) => {
      return a[props.order] > b[props.order] ? 1 : -1
    })
  })

</script>

<template>
 <div class="job-list">
  <p>
    ordre par {{ order }}
  </p>
  <ul style="display: flex;flex-direction: column;">
    <li v-for="job in orderedJobs" :key="job.id" style="list-style: none;">
      <span>{{ job.title }}</span> - <span>{{ job.salary }}</span> - <span>{{ job.location }}</span>
    </li>
  </ul>
 </div>
</template>

<style lang="scss" scoped>
  
</style>