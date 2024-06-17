<template>
  <div>
    <!-- 1. 자식컴포넌트에서 createPost 이벤트를 발생시킨다 -->
    <!--<button class="btn btn-primary mb-3" v-on:click="$emit('createPost')">Create</button>-->
    <!--<button class="btn btn-primary mb-3" v-on:click="$emit('createPost', 1, 2, 3, '김길동')">Create</button>-->
    <button class="btn btn-primary mb-3" v-on:click="createPost">button</button>

    <input type="text" class="form-control" v-model="title" />
    <button class="btn btn-primary mb-3" v-on:click="savePost">savePost</button>
    
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  //emits: ['createPost'],
  emits: {
    savePost: newTitle => {
      console.log('validator: ', newTitle);
      if( !newTitle){
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

    const title = ref('');
    const savePost = () => {
      emit('savePost', title.value );
    }

    return {
      createPost,
      title,
      savePost,
    }
  }
}
</script>

<style scoped>

</style>