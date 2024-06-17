<template>
  <main>
    <div class="container py-4">
      <MyCreatePost v-on:save-post="addPost" />

      <hr/>

      <div class="row g-3">
        <div class="col col-4"
        v-for="post in posts" :key="post.id"
        >
          <MyCard
          :title1="post.title" 
          :contents1="post.contents"
          :post-type1="post.postType"
          :is-like1="post.isLike"
          v-on:toggle-like2="post.isLike = !post.isLike"
          />
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import MyCard from '@/components/MyCard.vue'
import MyCreatePost from '@/components/MyCreatePost.vue'
import { reactive } from 'vue';

export default {
  components: {
    MyCard,
    MyCreatePost,
  },
  setup () {
    const posts = reactive([
      {id: 1, title: '제목1', contents: '내용1', postType: 'news', isLike: false },
      {id: 2, title: '제목2', contents: '내용2', postType: 'notice', isLike: true },
      {id: 3, title: '제목3', contents: '내용3', postType: 'news', isLike: false },
    ]);

    const addPost = (newPost) => {
      console.log("newPost", newPost);
      console.log("posts", posts);

      const { title, type } = newPost;
      posts.push({
        id: posts.length+1,
        title: title,
        postType: type,
        isLike: false,
      });

    };

    return {
      posts,
      addPost,
    }
  }
}
</script>

<style scoped>

</style>