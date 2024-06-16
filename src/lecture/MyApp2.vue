<template>
    <h2>보간법</h2>
    <p>{{ message }}</p>
    <p v-once>{{ message }}</p>
    <button v-on:click="message=message + '!'">click</button>
  <hr />
    <h2>HTML</h2>
    <p v-html="rawHtml"></p>
  <hr />
    <h2>속성바인딩</h2>
    <p v-bind:title="dynamicTitle">마우스를 올려보세요</p>
    <input type="text" value="홍길동" v-bind:disabled="isDisabled">
    <input v-bind="attrs" />
    <h2>JavaScript</h2>
    {{ message.split('').reverse().join('') }}<br />
    {{ isDisabled ? '예' : '아니오' }}
</template>

<script>
import { ref } from 'vue';

export default {
  setup () {
    const message = ref('안녕하세요');
    const rawHtml = ref('<span class="strong">안녕하세요</span>');
    const dynamicTitle = ref('안녕하세요@!@!@');
    const isDisabled = ref(true);
    const attrs = ref({
      type: "password",
      value: "123456",
      disabled: false,
    });

    return {
      message,
      rawHtml,
      dynamicTitle,
      isDisabled,
      attrs,
    }
  }
}
</script>

<style scoped>
  hr {
    margin: 10px 0;
  }
  .strong {
    font-weight: 700;
  }
</style>