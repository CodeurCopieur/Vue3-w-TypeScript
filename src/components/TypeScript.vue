<script setup lang="ts">
import { reactive, ref } from 'vue';

defineProps<{ msg: string }>()

const name = ref<string>('unknow');
const age = ref<number>(28);

const state = reactive({
  name: 'unknow',
  age: 28
});

function changeName(newName: string) {
  state.name = newName
  name.value = newName
}
function changeAge(newName: number) {
  state.age = newName
  age.value = newName
}
</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <button type="button" @click="changeName('Codwerk')">change Name ref : {{ name }} - reactive {{ state.name }}</button>
    <button type="button" @click="changeAge(29)">change Name ref : {{ age }} - reactive {{ state.age }}</button>
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
../types/job./types/job../types/job