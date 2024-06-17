<template>
  <main>
    <div class="container py-4">
      <div class="row g-3">
        <div class="col col-4"> <!-- add col-4 -->
          <AppCard1 title="제목1" contents="내용1" />
        </div>
        <div class="col col-4"> <!-- add col-4 -->
          <AppCard2 title="제목2" contents="내용2" />
        </div>
        <div class="col col-4" v-for="post in posts" :key="post.id">
          <AppCard 
            :title="post.titleValue" 
            :contents="post.contentsValue" 
            :type="post.type" 
            :isLike="post.isLike" 
          />
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import AppCard from '@/components/AppCard.vue';
import AppCard1 from '@/components/AppCard1.vue';
import AppCard2 from '@/components/AppCard2.vue';
import { reactive } from 'vue';

export default {
  components: {
    AppCard,
    AppCard1,
    AppCard2,
  },
  setup () {
    
    const posts = reactive([
      { id:1, titleValue:"제목11", contentsValue:"내용11", isLike: true, type: 'news'},
      { id:2, titleValue:"제목22", contentsValue:"내용22", isLike: true, type: 'news'},
      { id:3, titleValue:"제목33", contentsValue:"내용33", isLike: false, type: 'news'},
      { id:4, titleValue:"제목44", contentsValue:"내용44", isLike: false, type: 'notice'},
    ]);

    return {
      posts,
    }
  }
}
</script>

<style scoped>

</style>