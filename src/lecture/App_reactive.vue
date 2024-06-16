<template>
  <div>
    <button v-on:click="increment">click {{ state.count }}</button>
  </div>
</template>

<script>
import { reactive } from 'vue';

export default {
  setup () {
    const state = reactive({
      count: 0,
    })

    console.log( 'state typeof', typeof state );

    const increment = () => {
      state.count++;
    }

    return {
      state,
      increment,
    }
  }
}
</script>

<style scoped>

</style>