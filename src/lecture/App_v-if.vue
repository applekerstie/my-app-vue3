<template>
  <div>
    <h2 v-if="isVisible">hello vue3!</h2>
    <h2 v-else>false 입니다</h2>
    <button v-on:click="isVisible = !isVisible">toggle</button>
    <hr />

    <h2 v-if="type === 'A'">A입니다</h2>
    <h2 v-else-if="type === 'B'">B입니다</h2>
    <h2 v-else-if="type === 'C'">C입니다</h2>
    <h2 v-else>A,B,C 가 아닙니다</h2>

    <button v-on:click="type = 'A'">A</button>
    <button v-on:click="type = 'B'">B</button>
    <button v-on:click="type = 'C'">C</button>
    <button v-on:click="type = 'D'">D</button>
</div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup () {
    const isVisible = ref(false);
    const type = ref('A');

    return {
      isVisible,
      type,
    }
  }
}
</script>

<style scoped>

</style>