<template>
  <div :style="styleObject">
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla tempora repellat, saepe nostrum error aperiam, deleniti provident, aut quae rem reiciendis quasi asperiores fugit! Nisi iste accusamus quis cumque provident.
  </div>
  <button v-on:click="fontSize++">+</button>
  <button v-on:click="fontSize--">-</button>
</template>

<script>
import { computed, ref } from 'vue';

export default {
  setup () {
    /*
    const styleObject = {
      fontSize : '13px',
      color: 'red',
    }
    */
    const fontSize = ref(13);
    const color = ref('red');

    const styleObject = computed( ()=>{
      return {
        fontSize: fontSize.value + 'px',
        color: color.value,
      }
    });

    return {
      styleObject,
      fontSize,
    }
  }
}
</script>

<style scoped>

</style>