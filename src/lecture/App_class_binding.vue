<template>
  <!--
  <div class="text" :class="{ active: isActive, 'text-danger': hasError }">
    텍스트입니다
  </div>
  -->

  <div clsss="text" :class="classObject">
    텍스트입니다
  </div>
  <button v-on:click="toggle">toggle</button>
  <button v-on:click="hasError = !hasError">toggleError</button>

  <hr />

  <div class="text" :class="[isActive ? 'active-class' : 'class', errorClass]">
    텍스트입니다2
  </div>

</template>

<script>
import { computed, reactive, ref } from 'vue';

export default {
  setup () {
    const isActive = ref(true);
    const hasError = ref(false);

    /*
    const classObject = reactive({
      active: true,
      'text-danger': false,
    })
    */

    const classObject = computed( ()=> {
      return {
        active: isActive.value,
        'text-danger': true,
      }
    })

    const activeClass = ref('active');
    const errorClass = ref('error');

    const toggle = () => {
      isActive.value = !isActive.value;
    }

    return {
      isActive,
      toggle,
      hasError,
      classObject,
      activeClass,
      errorClass,
    }
  }
}
</script>

<style scoped>
.active {
  font-weight: 900;
}
.text-danger {
  color: red;
}
</style>