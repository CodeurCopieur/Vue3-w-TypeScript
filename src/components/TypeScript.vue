<script setup lang="ts">
import { ref } from 'vue'

defineProps<{ msg: string }>()

const name: Ref<string> = ref('unknow');
const age: Ref<number> = ref(28);

function changeName(newName: string) {
  name.value = newName
}
function changeAge(newName: number) {
  age.value = newName
}
</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <button type="button" @click="changeName('Codwerk')">change Name {{ name }}</button>
    <button type="button" @click="changeAge(29)">change Name {{ age }}</button>
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
