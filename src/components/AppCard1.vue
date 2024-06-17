<template>
  <div class="card">
    <div class="card-body">
      <span class="badge bg-secondary">New</span>
      <h5 class="card-title mt-2" :class="$style.red">{{ title }} {{ post.title }}</h5>
      <p class="card-text">{{ contents }} {{ post.contents }}</p>
      <a href="#" class="btn btn-primary">Go somewhere</a>
    </div>
  </div>
</template>

<script>
import { useCssModule, reactive } from 'vue'; 

export default {
  props: ['title', 'contents'],
  setup () {

    const style = useCssModule();
    console.log('style:', style);

    const post = reactive({
      title: '제목2',
      contents: '내용2',
    });

    return {
      post
    }
  }
}
</script>

<style module>
.red {
  color: red;
}
</style>