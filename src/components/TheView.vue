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
          <!-- 값전달시 kebob case 사용 -->
          <AppCard3 
            :title="post.titleValue" 
            :contents="post.contentsValue" 
            :type="post.type" 
            :is-like="post.isLike" 
          />
        </div>
        <div class="col col-4" v-for="post in posts2" :key="post.id">
          <AppCard4
            :title="post.titleValue" 
            :contents="post.contentsValue" 
            :type="post.type" 
            :is-like="post.isLike" 
          />
          <button v-on:click="post.isLike = !post.isLike">toggle</button>
        </div>
        <div class="col col-4" v-for="post in posts3" :key="post.id">
          <AppCard
            :title="post.titleValue" 
            :contents="post.contentsValue" 
            :type="post.type" 
            :is-like="post.isLike" 
            @toggle-like1="post.isLike = !post.isLike"
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
import AppCard3 from '@/components/AppCard3.vue';
import AppCard4 from '@/components/AppCard4.vue';

import { reactive } from 'vue';

export default {
  components: {
    AppCard,
    AppCard1,
    AppCard2,
    AppCard3,
    AppCard4,
  },
  setup () {
    
    const posts = reactive([
      { id:1, titleValue:"제목11", contentsValue:"내용11", isLike: true, type: 'news'},
      { id:2, titleValue:"제목22", contentsValue:"내용22", isLike: true, type: 'news'},
      { id:3, titleValue:"제목33", contentsValue:"내용33", isLike: false, type: 'news'},
      { id:4, titleValue:"제목44", contentsValue:"내용44", isLike: false, type: 'notice'},
    ]);

    const posts2 = reactive([
      { id:1, titleValue:"제목111", contentsValue:"내용111", isLike: true, type: 'notice11111'},
      { id:2, titleValue:"제목222", contentsValue:"내용222", isLike: true, type: 'notice'},
      { id:3, titleValue:"제목333", contentsValue:"내용333", isLike: false, type: 'notice'},
    ]);

    const posts3 = reactive([
      { id:1, titleValue:"제목1111", contentsValue:"내용1111", isLike: false, type: 'news'},
      { id:2, titleValue:"제목2222", contentsValue:"내용2222", isLike: false, type: 'news'},
      { id:3, titleValue:"제목3333", contentsValue:"내용3333", isLike: false, type: 'news'},
    ]);

    return {
      posts,
      posts2,
      posts3,
    }
  }
}
</script>

<style scoped>

</style>