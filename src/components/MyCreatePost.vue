<template>
  <div class="row g-3">
    <div class="col col-2">
      <select v-model="type2" class="form-select" aria-label="Default select example">
        <option selected>Open this select menu</option>
        <option value="news">뉴스</option>
        <option value="notice">공지사항</option>
      </select>
    </div>
    <div class="col col-8">
      <input v-model="title2" type="text" class="form-control" />
    </div>
    <div class="col col-2 d-grid">
      <button 
      class="btn btn-primary"
      v-on:click="savePost"
      >
      추가
      </button>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup (props, { emit }) {
    const type2 = ref('news');
    const title2 = ref('');
    const savePost = () => {
      const newPost = {
        title: title2.value,
        type: type2.value,
      };
      emit('savePost', newPost);

      type2.value = 'news';
      title2.value = '';

    };

    return {
      type2,
      title2,
      savePost,
    }
  }
}
</script>

<style scoped>

</style>