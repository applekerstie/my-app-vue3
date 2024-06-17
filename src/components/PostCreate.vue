<template>
  <div>
    <!-- 1. 자식컴포넌트에서 createPost 이벤트를 발생시킨다 -->
    <!--<button class="btn btn-primary mb-3" v-on:click="$emit('createPost')">Create</button>-->
    <!--<button class="btn btn-primary mb-3" v-on:click="$emit('createPost', 1, 2, 3, '김길동')">Create</button>-->

    <button class="btn btn-primary mb-3" v-on:click="createPost">button</button>
  </div>
</template>

<script>
export default {
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

    return {
      createPost,
    }
  }
}
</script>

<style scoped>

</style>