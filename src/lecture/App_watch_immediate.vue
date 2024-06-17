<template>
  <div>
    <p>{{ message }}</p>
    <p>{{ reverseMessage }}</p>
  </div>
</template>

<script>
import { ref, watch } from 'vue';

export default {
  setup () {
    const message = ref('hello vue3');
    const reverseMessage = ref('');

    /*
    watch( message, newValue => {
      reverseMessage.value = newValue.split('').reverse().join('');
    },
    {
      immediate: true,
    }
    );
    */

    const reverseFunction = (newValue) => {
      console.log("최초 즉시 실행함")
      reverseMessage.value = newValue.split('').reverse().join('');
    }
    reverseFunction( message.value);
    watch( message, reverseFunction);

    return {
      message,
      reverseMessage,
    }
  }
}
</script>

<style scoped>

</style>