<template>
  <div>
    <!-- 1. 자식컴포넌트에서 createPost 이벤트를 발생시킨다 -->
    <!--<button class="btn btn-primary mb-3" v-on:click="$emit('createPost')">Create</button>-->
    <!--<button class="btn btn-primary mb-3" v-on:click="$emit('createPost', 1, 2, 3, '김길동')">Create</button>-->
    <button class="btn btn-primary mb-3" v-on:click="createPost">button</button>
    
    <div class="row g-3">
      <div class="col col-2">
        <select v-model="typeValue" class="form-select" aria-label=".form-select-sm example">
          <option selected>Open this select menu</option>
          <option value="news">뉴스</option>
          <option value="notice">공지사항</option>
        </select>
      </div>
      <div class="col col-8">
        <input type="text" class="form-control" v-model="titleValue" />
      </div>
      <div class="col col-2 d-grid">
        <button class="btn btn-primary mb-3" v-on:click="savePost">추가</button>
      </div>     
    </div>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  //emits: ['createPost'],
  emits: {
    savePost: newPost => {
      if( !newPost.type){
        return false;
      }else if( !newPost.titleValue){
        return false;
      }
      return true;
    }
    
    // validation이 없을떄
    //savePost: null,
  },
  /*
  setup (props, context) {
    
    const createPost = () => {
      context.emit('createPost', 1, 2, 3, '김길동');
    }

    return {
      createPost,
    }
  }
  */
  setup (props, { emit }) {
    
    const createPost = () => {
      emit('createPost', 1, 2, 3, '김길동');
    }

    const typeValue = ref('news');
    const titleValue = ref('');

    const savePost = () => {
      const newPost = {
        titleValue: titleValue.value,
        type: typeValue.value,
      };
      emit('savePost', newPost );

      typeValue.value = 'news';
      titleValue.value = '';

    }

    return {
      createPost,
      titleValue,
      typeValue,
      savePost,
    }
  }
}
</script>

<style scoped>

</style>